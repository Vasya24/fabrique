<template>
  <div id="bottom">
    <header>
      <div class="header-content">
        <p class="header-plus">&plus;</p>
        <p>Нажмите, чтобы добавить новое условие выборки.</p>
        <p>Все условия связываются между собой логическим "И"</p>

      </div>
    </header>
    <div id="bottom-footer">
      <button class="test-survey">Протестировать опрос</button>
      <button class="next">Далее &rarr;</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Bottom"
}
</script>

<style scoped>
  #bottom {
    width: 1020px;
    position: absolute;
    background-color: #fff;
    top: 1467px;
  }
  #bottom > header {
    padding-top: 45px;
    padding-left: 40px;
    height: 230px;
  }
 .header-content {
   border-radius: 5px;
   box-sizing: border-box;
   border: 2px solid #E5ECF0;
   text-align: center;
   padding-top: 30px;
   padding-bottom: 32px;
   color: #0D7616;
   width: 940px
 }
 .header-plus {
   font-size: 50px;
 }
 #bottom-footer {
   height: 110px;
   width: 1020px;
   position: absolute;
   background-color: #F4F7F9;
 }
 #bottom-footer > button {
   border: none;
   position: relative;
   top: 30px;
 }
 .test-survey {
   width: 220px;
   height: 50px;
   color: #07A101;
   left: 40px;
 }
 .next {
   width: 121px;
   height: 50px;
   background-color: #0DA30E;
   color: #fff;
   left: 599px;
 }
</style>
