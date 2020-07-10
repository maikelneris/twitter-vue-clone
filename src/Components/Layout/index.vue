<template>
  <div id="layout">
    <div class="wrapper">
      <Main />
    </div>
  </div>
</template>

<script>
import Main from "../Main/index";
export default {
  components: {
    Main
  }
};
</script>

<style scoped>
#layout {
  background: var(--primary);
}
.wrapper {
  height: 100%;
  max-width: 1280px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
}
</style>