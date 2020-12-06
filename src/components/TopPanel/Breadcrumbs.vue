<template>
  <div id="breadcrumbs">
    <img src="@/assets/home.png" alt="home" class="home">
    <span class="next">&rarr;</span>
    <span class="previous-text">Опросы</span>
    <span class="next">&rarr;</span>
    <span class="current-text">Добавить опрос</span>
  </div>
</template>

<script>
export default {
name: "Breadcrumbs"
}
</script>

<style>

  #breadcrumbs {
    position: relative;
    top: 50px;
  }

  .home {
    position: relative;
    top: 5px;
    cursor: pointer;
  }

  .previous-text {
    cursor: pointer;
  }

  .next {
    margin-left: 6px;
    margin-right: 6px;
  }

  .current-text {
    color: #AAAAAA;
    cursor: pointer;
  }
</style>
