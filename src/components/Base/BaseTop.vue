<template>
  <nav id="base-top">
    <ul class="top-items">
      <li class="top-item"><span>Параметры</span></li>
      <li class="top-item"><span>Вопросы</span></li>
      <li class="top-item"><span>Логика</span></li>
      <li class="top-item"><span>Условия</span></li>
      <li class="top-item active"><span>Респонденты</span></li>
    </ul>
  </nav>
</template>

<script>
export default {
name: "BaseTop"
}
</script>

<style scoped>

#base-top {
  position: absolute;
  top: 155px;
  /*right: -275px;*/
}
  .top-items {
    display: flex;
    list-style: none;
    position: relative;
    width: 1020px;
    /*right: 900px;*/
    cursor: pointer;
    box-sizing: border-box;
    border-bottom: 1px solid #C1E80F;
    justify-content: space-evenly;
  }

  .top-item {
    height: 62px;
    box-sizing: border-box;
    color: #0F7717;
  }

  .top-item.active {
    border-bottom: 2px solid #C1E80F;
    color: #000;
  }

  .top-item span {
    position: relative;
    top: 26px;
  }
</style>
