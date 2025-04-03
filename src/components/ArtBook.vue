<template>
  <div class="art-book">
    <Flipbook
      class="flipbook"
      :pages="pages"
      :zooms="[1]"
      :startPage="pageNum"
      :singlePage="false"
      v-slot="flipbook"
      ref="flipbook"
      @flip-left-end="onFlipLeftEnd"
      @flip-right-end="onFlipRightEnd">
      <div class="flipbook-controls">
        <div
          v-if="flipbook.page > 1"
          class="nav-control previous"
          @click="pageFlip(flipbook.flipLeft)">
          <span>←</span>
        </div>
        <h4 class="text">
          Page {{flipbook.page}} of {{flipbook.numPages}}
        </h4>
        <div
          v-if="flipbook.page < flipbook.numPages"
          class="nav-control next"
          @click="pageFlip(flipbook.flipRight)">
          <span>→</span>
        </div>
      </div>
    </FlipBook>
  </div>
</template>

<script>
import Flipbook from 'flipbook-vue/vue2'

export default {
  name: 'ArtBook',

  components: {
    Flipbook
  },

  data() {
    return {
      pages: [
        null,
        'flipbook-pages/1.jpeg',
        // 'flipbook-pages/2.jpeg',
        // 'flipbook-pages/3.jpeg',
        // 'flipbook-pages/4.jpeg',
        // 'flipbook-pages/5.jpeg',
        // 'flipbook-pages/6.jpeg',
        // 'flipbook-pages/7.jpeg',
        // 'flipbook-pages/8.jpeg',
        // 'flipbook-pages/9.jpeg',
        // 'flipbook-pages/10.jpeg',
        // 'flipbook-pages/11.jpeg',
        // 'flipbook-pages/12.jpeg',
        // 'flipbook-pages/13.jpeg',
        // 'flipbook-pages/14.jpeg',
        // 'flipbook-pages/15.jpeg',
        // 'flipbook-pages/16.jpeg',
        // 'flipbook-pages/17.jpeg',
        // 'flipbook-pages/18.jpeg',
        // 'flipbook-pages/19.jpeg',
        // 'flipbook-pages/20.jpeg',
        // 'flipbook-pages/21.jpeg',
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
        // 'flipbook-pages/84.jpeg',
        // 'flipbook-pages/85.jpeg',
        // 'flipbook-pages/86.jpeg'
      ],
      pageNum: null,
      isFlipping: false
    }
  },

  methods: {
    onFlipLeftEnd(page) {
      window.location.hash = '#' + page
      this.isFlipping = false
    },
    onFlipRightEnd(page) {
      window.location.hash = '#' + page
      this.isFlipping = false
    },
    setPageFromHash() {
      const n = parseInt(window.location.hash.slice(1), 10)
      if (isFinite(n)) this.pageNum = n
    },
    pageFlip(flipPageMethod) {
      if (!this.isFlipping) {
        flipPageMethod()
        this.isFlipping = true
      }
    }
  },

  mounted() {
    window.addEventListener('keydown', (e) => {
      const flipbook = this.$refs.flipbook
      if (!flipbook) return
      if ((e.key === 'ArrowLeft' || e.keyCode === 37) && flipbook.canFlipLeft) {
        flipbook.flipLeft()
      }
      if ((e.key === 'ArrowRight' || e.keyCode === 39) && flipbook.canFlipRight) {
        flipbook.flipRight()
      }
    })
    window.addEventListener('hashchange', this.setPageFromHash)
    this.setPageFromHash()
  }
}
</script>

<style lang="scss" scoped>
.art-book {
  width: 100%;
  height: 90vh;
  @include browser {
    height: 75vh;
  }
}

.flipbook {
  width: 100%;
  height: 100%;
  display: flex;
  flex-flow: column-reverse;
  :deep(.bounding-box) {
    box-shadow: 4px 4px 11px 5px rgba(0,0,0,0.25);
  }
}


.flipbook-controls {
  display: flex;
  align-items: center;
  justify-content: center;
  @include browserLarge {
    padding: 2rem 0;
  }
  @include mobile {
    padding: 0;
    padding-top: 1rem;
  }
}

.nav-control {
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  font-size: toRem(18);
  height: toRem(45);
  width: toRem(45);
  margin: 0 1rem;
  border-radius: 50%;
  transition: 100ms ease-in;
  color: white;
    background-color: $yellow;
    box-shadow: inset -3px -4px 4px #fcf3cc, inset 3px 4px 4px #d9cb9a;
  &:hover {
    color: white;
    background-color: $blue;
    box-shadow: inset -3px -4px 4px #ccfcfa, inset 3px 4px 4px #9ad9cf;
  }
  &:active {
    color: white;
    background-color: $green;
    box-shadow: inset -3px -4px 4px #CCFD7C, inset 3px 4px 4px #9AD933;
  }


}

</style>
