<template>
  <div id="base">
    <BaseTop />
    <AddNewSurvey />
    <Container />
  </div>
</template>

<script>
import BaseTop from "@/components/Base/BaseTop";
import AddNewSurvey from "@/components/Base/AddNewSurvey";
import Container from "@/components/Base/Container";
export default {
  name: "Base",
  components: {
    BaseTop,
    AddNewSurvey,
    Container
  }
}
</script>

<style>
#base {
  display: flex;
  flex-direction: column;
  filter: drop-shadow(0px 1px 1px rgba(0,0,1,0.1));
  position: absolute;
  top: 0;
  left: 235px;
}
</style>
