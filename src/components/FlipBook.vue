<template>
  <div class="art-book">
    <object
      data="@/assets/ezio-marcelli-art-book.pdf"
      type="application/pdf"
      width="100%"
      height="100%">
    </object>
  </div>
</template>

<script>
export default {
name: 'FlipBook'
}
</script>

<style lang="scss" scoped>
.art-book {
  width: 95%;
  height: 90vh;
}

</style>
