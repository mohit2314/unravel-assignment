<template>
  <div
    class="progress__bar"
    :style="{
      'background-color': backgroundColor,
      'border-radius': borderRadius,
      color: fontColor,
    }"
  >
    <div
      class="progress__percentage"
      :style="{ 'background-color': computeProgressColor ,'width':progressPercentage + '%'}"
    >{{progressPercentage}}</div>
  </div>
</template>

<script>
export default {
  props: {
    progressPercentage: {
      type: Number,
    },
    borderRadius: {
      type: Number,
      default: 2,
    },
    backgroundColor: {
      type: String,
      default: "#D3D7DD",
    },
    fontColor: {
      type: String,
      default: "#fff",
    },
  },
  computed: {
    computeProgressColor() {
      if (this.progressPercentage > 0 && this.progressPercentage <= 40) {
        return "#2BC717";
      } else if (this.progressPercentage > 40 && this.progressPercentage <= 80) {
        return "#D54451";
      } else {
        return "#FFB902";
      }
    },
  },
};
</script>

<style lang="scss">
.progress__bar {
  width: 160px;
  height: 20px;
  text-align: center;
  font-size: 14px;

  .progress__percentage {
    max-width: 160px;
    height: 20px;
  }
}
</style>