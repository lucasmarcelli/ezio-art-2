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
  width: 65%;
  // @include tablet {
  //   width: 100%;
  // }
}

</style>
