<template>
<div id="container">
  <div class="conditions">
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
      <button type="button" class="delete" >

        Удалить условие
      </button>
    </div>
<!--    <ContainerItem />-->
  </div>
  <div id="footer">
    <form @submit.prevent="onSubmit">
      <button type="submit">Тык</button>
    </form>
  </div>
</div>
</template>

<script>
// import ContainerItem from "@/components/Base/ContainerItem";
export default {
name: "Container",
  components: {
  // ContainerItem
  },
  data() {
  return {
    items: []
  }
  },
  methods: {

    onSubmit() {
      let item = `
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
          <button type="button" class="delete">
        Удалить условие
      </button>
    </div>
`;
      document.querySelector('.conditions').insertAdjacentHTML('beforeend', item);
      let buttons = document.querySelectorAll('.delete');
      for (let button of buttons) {
        button.onclick = function(e) {
          // console.log(e.target.parentNode)
          e.target.parentNode.remove()
        }
      }
    },
    // onDelete() {
    //   // e.target.parentNode.remove();
    //   let buttons = document.querySelectorAll('.delete');
    //   for (let button of buttons) {
    //     button.onclick = function(e) {
    //       console.log(e.target.parentNode)
    //     }
    //   }
    // },
  }
}
</script>

<style>
  #container {
    position: relative;
    top: 300px;
    width: 1020px;
  }
  /*#container {*/
  /*  margin-bottom: 50px;*/
  /*}*/
  .container-item {
    background-color: #FAFAFA;
    height: 200px;
    box-sizing: border-box;
    border-top: 1px solid black;
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
  .container-item header {
    display: flex;
    position: relative;
    top: 37px;
    left: 40px;
  }
  .selection {
    box-sizing: border-box;
    border: 2px solid gray;
    border-radius: 5px;
    padding-left: 16px;
    height: 50px;
    width: 700px;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    position: relative;
    bottom: 13px;
    left: 149px;
  }
  .delete {
    box-sizing: border-box;
    border: 2px solid #FFD2D2;
    border-radius: 5px;
    width: 189px;
    height: 50px;
    color: #F43529;
    background-color: #fff;
    position: relative;
    top: 70px;
    left: 792px;
    cursor: pointer;
  }
</style>
