<template>
  <div id="top-panel">
    <div class="search-and-user">
  <Search />
    <User />
    </div>
    <div id="brcr-wrapper">
    <Breadcrumbs />
    </div>
  </div>
</template>

<script>
import Search from "@/components/TopPanel/Search";
import User from "@/components/TopPanel/User";
import Breadcrumbs from "@/components/TopPanel/Breadcrumbs";
export default {
name: "TopPanel",
  components: {
    Breadcrumbs,
  Search,
    User
}
}
</script>

<style>
  #top-panel {
    height: 188px;
    position: absolute;
    left: 235px;
    top: 0;
  }

  .search-and-user {
    display: flex;
  }

  #brcr-wrapper {
    position: relative;
    left: 62px;
    top: 50px;
  }
</style>
