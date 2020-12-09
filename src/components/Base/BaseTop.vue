<template>
  <nav id="base-top">
    <ul class="top-items">
      <li class="top-item" v-bind:class="{active: activeTab === 1}" v-on:click="activeTab = 1"><span>Параметры</span></li>
      <li class="top-item" v-bind:class="{active: activeTab === 2}" v-on:click="activeTab = 2"><span>Вопросы</span></li>
      <li class="top-item" v-bind:class="{active: activeTab === 3}" v-on:click="activeTab = 3"><span>Логика</span></li>
      <li class="top-item" v-bind:class="{active: activeTab === 4}" v-on:click="activeTab = 4"><span>Условия</span></li>
      <li class="top-item" v-bind:class="{active: activeTab === 5}" v-on:click="activeTab = 5"><span>Респонденты</span></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "BaseTop",
  data() {
return {
  activeTab: 5
}
  }
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
