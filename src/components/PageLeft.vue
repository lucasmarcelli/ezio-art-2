<template>
  <div class="left">

    <h1 class="left-title">ezio marcelli</h1>

    <div class="content">

      <div class="bio-wrapper">
        <img class="ezio-portrait" src="@/assets/ezio-marcelli.jpg" alt="this is his face"/>
        <MarkdownParser class="bio" :markdown="bio" />
        <div class="contact">
          <p v-html="contact" />
        </div>
      </div>

      <div class="essay">
        <MarkdownParser class="essay" :markdown="essay" />
        <p class="editor" v-html="editor" />
      </div>

    </div>

  </div>
</template>

<script>
import copy from '../content/index.json'
import MarkdownParser from './MarkdownParser.vue';

export default {
  name: 'PageLeft',

  components: {
    MarkdownParser
  },

  computed: {
    bio () { return copy.bio},
    contact () { return copy.contact },
    essay () { return copy.essay.en },
    editor () { return copy.essay.editor }
  }
}

</script>

<style lang="scss" scoped>

.left {
  display: flex;
  flex-flow: column nowrap;
  justify-content: flex-start;
  width: calc(42% + 2rem);
  margin-right: 2rem;
  @include tablet {
    position: relative;
    width: 100%;
  }
  @include mobile {
    padding: 0;
  }
}

.content {
  z-index: 10;
  padding-right: 2rem;
  // height: 100%;
  overflow-y: auto;
  @include tablet {
    padding: 1rem 9rem 3rem 1rem;
  }
  @include mobile {
    padding: 0 1rem;
  }
}

.left-title {
  margin: 2rem 0 0;
  padding-bottom: 2rem;
  background-image: linear-gradient($light 50%, transparent 90%);
  @include siteTitle;
  @include browserLarge {
    margin: 3rem 0;
  }
  @include browserMed {
    margin: 2rem 0;
  }
  @include tablet {
    display: none;
  }
}

.bio-wrapper {
  @include tablet {
  }
  @include mobile {
    margin-right: 0;
  }
}

.ezio-portrait {
  height: 10rem;
  float: left;
  margin-right: 1rem;
  object-fit: contain;
}

.bio {
  font-size: clamp(1.2rem, 1.4vw, 1.3rem);
  margin: 0;
  @include browserMed {
    font-size: clamp(1rem, 1.4vw, 1.3rem);
  }
  @include tablet {
    font-size: 1.2rem;
  }
}

.contact {
  font-size: 1rem;
}

.essay {
  font-size: clamp(1rem, 1.4vw, 1.3rem);
}

.editor {
  text-align: right;
}

</style>
