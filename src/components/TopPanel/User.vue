<template>
  <div class="current-user">
  <div class="user-pic"></div>
  <p class="user-text">
    <span class="user-name">Alexander C.</span>
    <span class="user-status">Администратор</span>
  </p>
  </div>

</template>

<script>
export default {
name: "User"
}
</script>

<style>
.current-user {
  display: flex;
  flex-direction: row;
  position: absolute;
  left: 820px;
  top: 29px;
}
.user-pic {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background-color: blue;
  cursor: pointer;
}

.user-text {
  display: flex;
  flex-direction: column;
  position: relative;
  top: 12px;
  left: 10px;
}

.user-name {
  font-weight: 600;
}

.user-status {
  font-family: Helvetica;
  font-weight: 300;
  filter: grayscale(70%)
}


</style>
