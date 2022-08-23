<template>
  <div class="page__container">
    <!-- utility bar section  -->
    <div class="header__row">
      <div class="new__budget__cta">New Budget</div>
      <div class="search__bar">
        <input type="search" name="search" placeholder="Search..."/>
      </div>
    </div>
    <!-- Main table section -->
    <div class="main__table__section">
      <div class="section__header">
        <span>Active</span><span><i class="light-icon-info-circle"></i></span>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "HomeView",
  components: {},
};
</script>

<style lang="scss">
.page__container {
  display: flex;
  flex-direction: column;
  gap: 28px;

  .header__row {
    display: flex;
    justify-content: space-between;

    .new__budget__cta{
      padding: 8px 36px;
      background-color: #4AB9D9;
      color: #fff;
      border-radius: 4px;
      cursor: pointer;
    }

    .search__bar{
      width: 20%;
      input{
        width: 100%;
        border: 1px solid grey;
        padding: 6px;
        border-radius: 4px;
        outline: none;
      }
    }

  }

  .main__table__section {
    background-color: #f5f7fa;

    .section__header{
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 20px;
    }
  }
}
</style>
