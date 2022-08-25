<template>
  <div class="tag__component" :style="{'background-color':backgroundColor,'border-radius':borderRadius+'px','color':fontColor}">
<span>{{value}}</span>
  </div>
</template>

<script>
export default {
props:{
    value:{
        type:String
    },
    borderRadius:{
        type:Number,
        default:16 
    },
    backgroundColor:{
        type:String,
        default:'#444964'
    },
    fontColor:{
        type:String,
        default:'#fff'
    }
}
}
</script>

<style lang="scss">
.tag__component{
padding: 2px 8px;
font-size: 13px;
text-align: center;
}

</style>