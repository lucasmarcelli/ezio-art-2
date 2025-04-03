<template>
  <div class="right">
    <slot />
</div>
</template>

<script>
export default {
  name: "PageRight"
}
</script>

<style lang="scss" scoped>
.right {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: calc(60% - 2rem);
  position: relative;
  @include tablet {
    width: 100%;
  }
  @include mobile {
    justify-content: center;
    margin-bottom: 1rem;
  }
}

</style>
