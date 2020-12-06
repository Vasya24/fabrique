<template>
  <div id="app">
    <LeftPanel />
    <TopPanel />
    <Base />
  </div>
</template>

<script>
import LeftPanel from "@/components/LeftPanel/LeftPanel";
import TopPanel from "@/components/TopPanel/TopPanel";
import Base from "@/components/Base/Base";
export default {
  name: 'App',
  components: {
    LeftPanel,
    TopPanel,
    Base
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*display: flex;*/
  /*flex-direction: row;*/
}
</style>
