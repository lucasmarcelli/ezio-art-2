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
        <div 
          v-if="flipbook.page >= flipbook.numPages"
          @click="goToPage(1)" 
          class="nav-control next"
        >
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

  props: {
    pages: {
      type: Array,
      required: true
    }
  },

  data() {
    return {
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
    },
    goToPage(page) {
      this.pageNum = page
      this.$refs.flipbook.goToPage(page)
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
  max-height: 90vh;
  aspect-ratio: 17 / 14;
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
