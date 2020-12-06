<template>
  <div id="left-panel">
<div id="red-circle"></div>
    <ul id="panel-items">
      <li class="panel-item">
        <img src="@/assets/surveys-small.png" alt="survey" id="survey">
        <p class="sign">Опросы</p>
      </li>
      <li class="panel-item selected">
        <img src="@/assets/users.png" alt="users" id="users">
        <p class="sign">Пользователи</p>
      </li>
      <li class="panel-item">
        <img src="@/assets/blacklists.png" alt="black lists" id="blacklists">
        <p class="sign">Чёрные списки</p>
      </li>
      <li class="panel-item">
        <img src="@/assets/call-center.png" alt="call-center" id="call-center">
        <p class="sign">Колл-центр</p>
      </li>
    </ul>
    <div id="help">?</div>
  </div>
</template>

<script>
export default {
name: "LeftPanel"
}
</script>

<style scoped>

  ul {
    list-style: none;
  }

  #left-panel {
    box-sizing: border-box;
    border-right: 1px solid #EDEDED;
    border-bottom: 1px solid #EDEDED;
    width: 176px;
    height: 1628px;
    display: flex;
    flex-direction: column;
  }

  #red-circle {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background-color: #E52100;
    position: relative;
    left: 62px;
    top: 25px;
  }

  #panel-items {
    position: absolute;
    top: 150px;
  }

  .panel-item {
    width: 155px;
    height: 115px;
    box-sizing: border-box;
    border-radius: 25px;
    position: relative;
    left: 10px;
    margin-bottom: 11px;
    cursor: pointer;
  }

  .panel-item.selected {
    border: 2px solid #DBF284;
  }

  .panel-item.selected:hover {
    background-color: #fff;
  }

  .panel-item:hover {
    background-color: #F7F7F7;
  }

  .panel-item img {
    position: relative;
  }

  #survey {
    left: 59px;
    top: 20px;
  }

  #users {
    left: 50px;
    top: 22px;
  }

  #blacklists {
    width: 38px;
    height: 47px;
    top: 17px;
    left: 59px;
  }

  #call-center {
    width: 43px;
    height: 43px;
    left: 56px;
    top: 20px;
  }

  .sign {
    font-size: 12px;
    position: relative;
    top: 30px;
    text-align: center;
  }

  #survey {
    width: 39px;
    height: 48px;
  }

  #help {
    position: relative;
    top: 1111px;
    left: 66px;
    width: 43px;
    height: 43px;
    border-radius: 50%;
    border: 2px solid black;
    color: #0DA30E;
    padding-top: 7px;
    padding-left: 15px;
    box-sizing: border-box;
    font-size: 19px;
  }

</style>
