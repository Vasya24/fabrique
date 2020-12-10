<template>
  <div class="container-item">
    <header>
      <p class="condition-label">Условие <span></span></p>
      <select name="selection" class="selection">
        <option value="">Выберите условие</option>
        <option value="age">Возраст респондента</option>
        <option value="card-type">Тип карты лояльности</option>
        <option value="card-status">Статус карты лояльности</option>
      </select>
    </header>
    <div class="item-contents">

    </div>
  </div>
</template>

<script>
export default {
name: "ContainerItem",

}
</script>

<style scoped>
  .container-item {
    background-color: #FAFAFA;
  }
  .container-item.age-variant {
    background-color: #FFFCF5;
  }
  .container-item.type-variant {
    background-color: #F8FAFF;
  }
  .container-item.status-variant {
    background-color: #FAFFF8;
  }
  .container-item > header {
    display: flex;
    margin-bottom: 50px;
  }
</style>
