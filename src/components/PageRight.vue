<template>
  <div class="right">
    <ArtBook :pages="pages" />
</div>
</template>

<script>
import ArtBook from './ArtBook'

export default {
  name: "PageRight",

  components: {
    ArtBook
  },

  data() {
    return {
      isMobile: null
    }
  },

  computed: {
    pages() {
      return [
        null,
        'flipbook-pages/1.jpeg',
        'flipbook-pages/22.jpeg',
        'flipbook-pages/23.jpeg',
        'flipbook-pages/24.jpeg',
        'flipbook-pages/25.jpeg',
        'flipbook-pages/26.jpeg',
        'flipbook-pages/27.jpeg',
        'flipbook-pages/28.jpeg',
        'flipbook-pages/29.jpeg',
        'flipbook-pages/30.jpeg',
        'flipbook-pages/31.jpeg',
        'flipbook-pages/32.jpeg',
        'flipbook-pages/33.jpeg',
        'flipbook-pages/34.jpeg',
        'flipbook-pages/35.jpeg',
        'flipbook-pages/36.jpeg',
        'flipbook-pages/37.jpeg',
        'flipbook-pages/38.jpeg',
        'flipbook-pages/39.jpeg',
        'flipbook-pages/40.jpeg',
        'flipbook-pages/41.jpeg',
        'flipbook-pages/42.jpeg',
        'flipbook-pages/43.jpeg',
        'flipbook-pages/44.jpeg',
        'flipbook-pages/45.jpeg',
        'flipbook-pages/46.jpeg',
        'flipbook-pages/47.jpeg',
        'flipbook-pages/48.jpeg',
        'flipbook-pages/49.jpeg',
        'flipbook-pages/50.jpeg',
        'flipbook-pages/51.jpeg',
        'flipbook-pages/52.jpeg',
        'flipbook-pages/53.jpeg',
        'flipbook-pages/54.jpeg',
        'flipbook-pages/55.jpeg',
        'flipbook-pages/56.jpeg',
        'flipbook-pages/57.jpeg',
        'flipbook-pages/58.jpeg',
        'flipbook-pages/59.jpeg',
        'flipbook-pages/60.jpeg',
        'flipbook-pages/61.jpeg',
        'flipbook-pages/62.jpeg',
        'flipbook-pages/63.jpeg',
        'flipbook-pages/64.jpeg',
        'flipbook-pages/65.jpeg',
        'flipbook-pages/66.jpeg',
        'flipbook-pages/67.jpeg',
        'flipbook-pages/68.jpeg',
        'flipbook-pages/69.jpeg',
        'flipbook-pages/70.jpeg',
        'flipbook-pages/71.jpeg',
        'flipbook-pages/72.jpeg',
        'flipbook-pages/73.jpeg',
        'flipbook-pages/74.jpeg',
        'flipbook-pages/75.jpeg',
        'flipbook-pages/76.jpeg',
        'flipbook-pages/77.jpeg',
        'flipbook-pages/78.jpeg',
        'flipbook-pages/79.jpeg',
        'flipbook-pages/80.jpeg',
        'flipbook-pages/81.jpeg',
        'flipbook-pages/82.jpeg',
        'flipbook-pages/83.jpeg',
      ]
    }
  },

  beforeMount() {
    if (window.innerWidth < 850)  {
      this.isMobile = true
    } else {
      this.isMobile = false
    }
  }
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
