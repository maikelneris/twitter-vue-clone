<template>
  <button class="button" :class="{ 'button-outline': outline }">
    <slot />
  </button>
</template>

<script>
export default {
  props: {
    outline: Boolean
  }
};
</script>

<style lang="scss" scoped>
.button {
  background: var(--twitter);
  color: var(--white);
  border: none;
  padding: 16px;
  border-radius: 25px;
  font-weight: bold;
  font-size: 15px;
  cursor: pointer;
  outline: 0;

  &:hover {
    background: var(--twitter-light-hover);
  }
}

.button-outline {
  background-color: transparent;
  color: var(--twitter);
  border: solid 1px var(--twitter);

  &:hover {
    background-color: var(--twitter-dark-hover);
  }
}
</style>
