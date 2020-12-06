<template>
  <div id="conditions">
    <div class="cond-item">
      <header>
        <label for="selection">Условие 1</label>
        <select name="selection" id="selection" class="selection">
          <option value="">Выберите условие</option>
          <option value="age" selected>Возраст респондента</option>
          <option value="card-type">Тип карты лояльности</option>
          <option value="сard-status">Статус карты лояльности</option>
        </select>
      </header>
      <div class="range one">
        <span>Диапазон 1</span>
        <div class="inputs one">
          <label for="from-one">от</label>
          <input type="text" id="from-one">
          <label for="to-one">до</label>
          <input type="text" id="to-one">
        </div>
      </div>
      <div class="range two">
        <button id="or">или</button>
        <span>Диапазон 2</span>
        <div class="inputs two">
          <label for="from-one">от</label>
          <input type="text" id="from-two">
          <label for="to-one">до</label>
          <input type="text" id="to-two">
        </div>
      </div>
      <footer>
        <button id="add-range"><span>&plus;</span> Добавить диапазон</button>
        <button class="delete-condition"><img src="@/assets/delete.png" alt="delete"> Удалить условие</button>

      </footer>
    </div>
    <div class="cond-item">
      <button id="and">И</button>
      <header>
        <label for="selection-two">Условие 2</label>
        <select name="selection" id="selection-two" class="selection">
          <option value="">Выберите условие</option>
          <option value="age">Возраст респондента</option>
          <option value="card-type" selected>Тип карты лояльности</option>
          <option value="сard-status">Статус карты лояльности</option>
        </select>
      </header>
      <label for="typeofcard">Тип 1</label>
      <select id="typeofcard">
        <option value="">Выберите тип</option>
        <option value="gold">Gold</option>
        <option value="silver">Silver</option>
        <option value="regular">Regular</option>
      </select>
      <footer>

        <button id="add-type"><span>&plus;</span> Добавить тип</button>
        <button class="delete-condition"><img src="@/assets/delete.png" alt="delete"> Удалить условие</button>

      </footer>

    </div>
    <div class="cond-item">
      <button id="and-two">И</button>
      <header>
        <label for="selection-three">Условие 3</label>
        <select name="selection" id="selection-three" class="selection">
          <option value="">Выберите условие</option>
          <option value="age">Возраст респондента</option>
          <option value="card-type">Тип карты лояльности</option>
          <option value="сard-status" selected>Статус карты лояльности</option>
        </select>
      </header>
      <label for="statusofcard">Тип 1</label>
      <select id="statusofcard">
        <option value="">Выберите статус</option>
        <option value="gold">Активна</option>
        <option value="silver">Заблокирована</option>
        <option value="regular">Перевыпускается</option>
      </select>
      <footer>

        <button id="add-status"><span>&plus;</span> Добавить статус</button>
        <button class="delete-condition"><img src="@/assets/delete.png" alt="delete"> Удалить условие</button>

      </footer>


    </div>
    <div class="cond-item">
      <header>
        <label for="selection-four">Условие 3</label>
        <select name="selection" id="selection-four" class="selection">
          <option value="">Выберите условие</option>
          <option value="age">Возраст респондента</option>
          <option value="card-type">Тип карты лояльности</option>
          <option value="сard-status">Статус карты лояльности</option>
        </select>
      </header>

    </div>
  </div>
</template>

<script>
export default {
name: "Conditions"
}
</script>

<style>

#conditions {
  position: relative;
  top: 285px;
  width: 1020px;
  height: 100px
}

  .cond-item {
    position: relative;
    width: 100%;
    padding-left: 40px;
    padding-top: 20px;
  }
  .cond-item:nth-child(1) {
    height: 381px;
    background-color: #FFFCF5;
    box-sizing: border-box;
    border-bottom: 1px solid #E3E3E3;
  }
  .cond-item:nth-child(2) {
    height: 311px;
    background-color: #F8FAFF;
    box-sizing: border-box;
    border-bottom: 1px solid #E3E3E3;
  }
  .cond-item:nth-child(3) {
    height: 291px;
    background-color: #FAFFF8;
    box-sizing: border-box;
    border-bottom: 1px solid #E3E3E3;
  }
  .cond-item:nth-child(4) {
    height: 199px;
    background-color: #FAFAFA;
    width: 980px;
  }
  .selection {
    position: relative;
    left: 149px;
    width: 700px;
    height: 50px;
    box-sizing: border-box;
    border: 2px solid #E3E3E3;
    border-radius: 5px;
    padding-left: 16px;
  }
  label[for="selection"] {
    color: #A37200;
    font-weight: bold;
  }
  .range > span {
    position: relative;
    top: 14px;
  }
  .range.one {
    display: flex;
    position: relative;
    top: 40px;
  }
  .range.two {
    display: flex;
    position: relative;
    top: 90px;
  }
  #or {
    border: none;
    border-radius: 5px;
    width: 60px;
    height: 50px;
    background-color: #F7F1E2;
    margin-right: 21px;
  }
  .range > span:nth-child(1) {
    margin-right: 154px;
  }
  .range > span:nth-child(2) {
    margin-right: 70px;
  }
  input {
    box-sizing: border-box;
    border: 2px solid #E3E3E3;
    height: 50px;
    border-radius: 5px;
  }
  #from-one, #from-two {
    width: 117px;
  }
  .inputs label {
    margin-right: 7px;
    margin-left: 19px;
  }
  footer {
    position: relative;
    top: 100px;
    left: 240px;
  }
  button {
    box-sizing: border-box;
    border: 2px solid;
    border-radius: 5px;
    height: 50px;
    background-color: #fff;
    cursor: pointer;
  }
  .delete-condition {
    border-color: #FFD2D2;
    color: #F5463B;
    position: relative;
  }
  #and {
    border: none;
    background-color: #E5F0FA;
    width: 60px;
    height: 50px;
    z-index: 999;
    position: absolute;
    top: -25px;
  }
  label[for="selection-two"] {
    font-weight: bold;
    color: #254AAB;
  }
  .cond-item:nth-child(n+2) > header {
    margin-bottom: 40px;
  }
  #typeofcard, #statusofcard {
    height: 50px;
    width: 620px;
    position: relative;
    border-radius: 5px;
    left: 187px;
    padding-left: 16px;
  }
  .cond-item:nth-child(1) > footer > .delete-condition {
    left: 304px;
    font-size: 16px;
  }
  .cond-item:nth-child(2) > footer > .delete-condition {
    left: 352px;
    font-size: 16px;
  }
  .cond-item:nth-child(3) > footer > .delete-condition {
  left: 333px;
  font-size: 16px;
}
  .cond-item:nth-child(n+2) > footer {
    position: relative;
    top: 50px;
  }
  #add-type {
  border-color: #DBF284;
  color: #81A500;
  width: 160px;
  font-weight: 300;
  font-size: 18px;
}
  #add-range > span {
  font-size: 16px;
}
  #add-range {
  border-color: #DBF284;
  color: #81A500;
  width: 208px;
  font-weight: 300;
  font-size: 18px;
}
  #add-range > span {
  font-size: 16px;
}
  #add-status {
    border-color: #DBF284;
    color: #81A500;
    width: 179px;
    font-weight: 300;
    font-size: 18px;
  }
  #add-status > span {
    font-size: 16px;
  }
  #and-two {
    background-color: #E7F6DA;
    border: none;
    width: 60px;
    height: 50px;
    z-index: 999;
    position: absolute;
    top: -25px;
  }
</style>
