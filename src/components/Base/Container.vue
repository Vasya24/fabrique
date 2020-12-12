<template>
<div id="container">
  <div class="conditions">
  </div>
  <div id="footer">
    <form @submit.prevent="onSubmit">
      <button type="submit" id="form-button">
        <div id="btn-text">
        <p id="plus">+</p>
        <p id="descr">Нажмите, чтобы добавить новое условие выборки. Все условия связываются между собой логическим "И"</p>
        </div>
      </button>
    </form>
  </div>
  <footer id="final">
    <button id="test">Протестировать опрос</button>
    <button id="next">Далее<span>&rarr;</span></button>
  </footer>
</div>
</template>

<script>
export default {
name: "Container",
  methods: {

    onSubmit() {
      let item = `
<div class="container-item">
<header>
      <p class="condition-label">Условие <span></span></p>
              <select name="selection" class="selection">
                <option value="none">Выберите условие</option>
                <option value="age" >Возраст респондента</option>
                <option value="card-type" >Тип карты лояльности</option>
                <option value="card-status" >Статус карты лояльности</option>
              </select>
    </header>
            <div class="form-control">
          <button type="button" class="delete">
        Удалить условие
      </button>
      </div>
    </div>
`;
      document.querySelector('.conditions').insertAdjacentHTML('beforeend', item);


      let buttons = document.querySelectorAll('.delete');
      for (let button of buttons) {
        button.addEventListener('click', function(e) {
          // e.target.parentNode.parentNode.remove()

          e.target.closest('.container-item').remove()
        })
      }

      let ages = document.querySelectorAll('option[value="age"]'),
          types = document.querySelectorAll('option[value="card-type"]'),
          status = document.querySelectorAll('option[value="card-status"]');

      let contItem;

      for (let age of ages) {
        contItem = age.closest('.container-item');
        age.addEventListener('click', () => {
          contItem.children[1].remove();

          let ageBox = `
                  <div class="age-box">
        <div class="range">
          <span class="range-mark">Диапазон</span>
          <span class="from">от</span><input type="text" class="from-input">
          <span class="to">до</span><input type="text" class="to-input">
        </div>
        <div class="form-control">
        <button class="add-range">Добавить диапазон</button>
                  <button type="button" class="delete delete-age">
        Удалить условие
      </button>
      </div>
      </div>

            `
          let nextRange = `
                  <div class="range">
          <span class="range-mark">Диапазон</span>
          <span class="from">от</span><input type="text" class="from-input">
          <span class="to">до</span><input type="text" class="to-input">
        </div>
          `
          contItem.children[0].insertAdjacentHTML('afterend', ageBox);
            let range = document.querySelectorAll('.range');
            let addRng = document.querySelectorAll('.add-range');
            for (let a of addRng) {
              for (let r of range) {
                a.onclick = () => {
                  r.insertAdjacentHTML('beforeend', nextRange)
                }
              }
            }
            contItem.classList.remove('type-variant', 'status-variant')
            contItem.classList.add('age-variant')
            let ageDelete = document.querySelectorAll('.delete-age');
            for (let ad of ageDelete) {
            ad.onclick = () => {
                ad.closest('.age-variant').remove()
              }
            }
        })
        }


      for (let type of types) {
        contItem = type.closest('.container-item')
        type.onclick = () => {
          contItem.children[1].remove();
          let typeBox = `
                <div class="type-box">
        <div class="type">
          <span class="type-mark">Тип</span>
          <select name="type-selection" class="type-selection">
            <option value="">Выберите тип карты</option>
            <option value="silver">Silver</option>
            <option value="gold">Gold</option>
            <option value="platinum">Platinum</option>
          </select>
        </div>
        <div class="form-control">
        <button class="add-type">Добавить тип</button>
        <button type="button" class="delete delete-type">
        Удалить условие
      </button>
      </div>
      </div>
          `
          let typeSel = `
                  <div class="type">
          <span class="type-mark">Тип</span>
          <select name="type-selection" class="type-selection">
            <option value="">Выберите тип карты</option>
            <option value="silver">Silver</option>
            <option value="gold">Gold</option>
            <option value="platinum">Platinum</option>
          </select>
        </div>
`
          contItem.children[0].insertAdjacentHTML('afterend', typeBox);

          let typ = document.querySelectorAll('.type');
          let addType= document.querySelectorAll('.add-type');
          for (let a of addType) {
            for (let t of typ) {
              a.onclick = () => {
                t.insertAdjacentHTML('afterbegin', typeSel)
              }
            }
          }

          contItem.classList.remove('age-variant', 'status-variant')
          contItem.classList.add('type-variant')
          let typeDelete = document.querySelectorAll('.delete-type');
          for (let td of typeDelete) {
            td.onclick = () => {
              td.closest('.type-variant').remove()
            }
          }
        }
      }

      for (let stat of status) {
        contItem = stat.closest('.container-item')
        stat.onclick = () => {
          contItem.children[1].remove();

          let statusBox = `
      <div class="status-box">
        <div class="status">
          <span class="status-mark">Тип</span>
          <select name="status-selection" class="status-selection">
            <option value="">Статус карты лояльности</option>
            <option value="issued">Выпущена</option>
            <option value="active">Активна</option>
            <option value="blocked">Заблокирована</option>
            <option value="reissued">Перевыпускается</option>
          </select>
        </div>
        <div class="form-control">
        <button class="add-status">Добавить статус</button>
        <button type="button" class="delete delete-status">
        Удалить условие
      </button>
      </div>
      </div>


          `
          let statusSel = `
        <div class="status">
          <span class="status-mark">Тип</span>
          <select name="status-selection" class="status-selection">
            <option value="">Статус карты лояльности</option>
            <option value="issued">Выпущена</option>
            <option value="active">Активна</option>
            <option value="blocked">Заблокирована</option>
            <option value="reissued">Перевыпускается</option>
          </select>
        </div>
`
          contItem.children[0].insertAdjacentHTML('afterend', statusBox);

          let stat = document.querySelectorAll('.status');
          let addStatus= document.querySelectorAll('.add-status');
          for (let a of addStatus) {
            for (let s of stat) {
              a.onclick = () => {
                s.insertAdjacentHTML('afterbegin', statusSel)
              }
            }
          }

          contItem.classList.remove('age-variant', 'type-variant')
          contItem.classList.add('status-variant');
          let statDelete = document.querySelectorAll('.delete-status');
          for (let sd of statDelete) {
            sd.onclick = () => {
              sd.closest('.status-variant').remove()
            }
          }
        }
      }
    },
  }
}
</script>

<style>
  #container {
    position: relative;
    top: 300px;
    width: 1020px;
  }
  .container-item {
    background-color: #FAFAFA;
    min-height: 200px;
    box-sizing: border-box;
    border-top: 1px solid black;
    display: flex;
    flex-direction: column;
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
    margin-bottom: 15px;
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
  .age-box, .type-box, .status-box {
    position: relative;
    margin-top: 58px;
  }
  .from, .to {
    margin-right: 7px;
    font-weight: lighter;
  }
  .to {
    margin-left: 19px;
  }
  .from-input, .to-input {
    box-sizing: border-box;
    height: 50px;
    width: 117px;
    border: 2px solid #E3E3E3;
    border-radius: 5px;
  }
  .range-mark {
    margin-left: 40px;
    margin-right: 165px;
    font-weight: 200;
  }
  .range {
    margin-top: 10px;
  }
  /* .add-range{*/
  /*  box-sizing: border-box;*/
  /*  border: 2px solid #DBF284;*/
  /*  color: #97B512;*/
  /*  background-color: #fff;*/
  /*  height: 50px;*/
  /*  width: 208px;*/
  /*  border-radius: 5px;*/
  /*  position: relative;*/
  /*  bottom: 10px;*/
  /*  left: 280px;*/
  /*}*/
  .form-control {
    margin-top: 20px;
    margin-bottom: 20px;
    display: flex;
    position: relative;
    right: -300px;
  }
  .add-range, .add-type, .add-status {
    box-sizing: border-box;
    border: 2px solid #DBF284;
    color: #97B512;
    background-color: #fff;
    height: 50px;
    width: 208px;
    border-radius: 5px;
    /*position: relative;*/
    /*bottom: -10px;*/
    /*left: 280px;*/
    cursor: pointer;
  }
  .delete {
    box-sizing: border-box;
    border: 2px solid #FFD2D2;
    border-radius: 5px;
    width: 189px;
    height: 50px;
    color: #F43529;
    background-color: #fff;
    margin-left: 30px;
    cursor: pointer;
  }

  .type, .status {
    margin-bottom: 10px;
  }
  .type-mark, .status-mark {
    margin-left: 40px;
  }
  .type-selection, .status-selection {
    box-sizing: border-box;
    width: 620px;
    height: 50px;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    position: relative;
    bottom: 13px;
    left: 186px;
    border: 2px solid #FFD2D2;
    border-radius: 5px;
    padding-left: 16px;
  }
  #footer {
    width: 1020px;
    background-color: #fff;
  }
  #form-button {
    box-sizing: border-box;
    border: 2px solid #E5ECF0;
    border-radius: 10px;
    width: 940px;
    background-color: #fff;
    color: #2AAF3A;
    cursor: pointer;
    text-align: center;
    margin: 45px 40px 45px 40px;
  }
  #btn-text {
    word-wrap: break-word;
    text-align: center;
    margin-top: 15px;
    margin-bottom: 15px;

  }
  #plus {
    font-size: 5rem;
    font-weight: 100
  }
  #descr {
    font-size: 1.3rem
  }
  #final {
    background-color: #F4F7F9;
    padding-top: 30px;
    padding-left: 40px;
  }
  #test {
    box-sizing: border-box;
    border-radius: 5px;
    border: none;
    border-bottom: 1px solid #C7CACC;
    background-color: #fff;
    color: #2AAF3A;
    width: 220px;
    height: 50px;
    cursor: pointer;
    margin-bottom: 30px;
  }
  #next {
    width: 121px;
    height: 50px;
    background-color: #2AAF3A;
    color: #fff;
    border: none;
    border-radius: 5px;
    margin-left: 599px;
    cursor: pointer;
  }
  #next > span {
    margin-left: 6px;
  }
</style>
