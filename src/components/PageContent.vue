<template>
  <div class="page-content">
    <slot />
</div>
</template>

<script>
export default {
  name: "PageContent"
}
</script>

<style lang="scss" scoped>
.page-content {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 65%;
  position: relative;
  @include tablet {
    width: 100%;
  }
  @include mobile {
    justify-content: center;
    margin-bottom: 2rem;
  }
}

</style>
