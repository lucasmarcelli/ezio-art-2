<template>
  <div class="left">

    <h1 class="left-title">ezio marcelli</h1>

    <div class="tabs">
      <div
        :class="['tab-about', { selected: tabSelected === 'about' }]"
        @click="() => tabSelected = 'about'">
        About
      </div>
      <div
        :class="['tab-foreward', { selected: tabSelected === 'foreward' }]"
        @click="() => tabSelected = 'foreward'">
        Rememberances of the Future – Foreward
      </div>
    </div>

    <div class="content">

      <div :class="['about-wrapper', { selected: tabSelected === 'about' }]">
        <img class="ezio-portrait" src="@/assets/ezio-marcelli.jpg" alt="this is his face"/>
        <MarkdownParser class="bio" :markdown="bio" />
        <div class="contact">
          <p v-html="contact" />
        </div>
      </div>

      <div :class="['foreward-wrapper', { selected: tabSelected === 'foreward' }]">
        <MarkdownParser class="foreward" :markdown="foreward" />
        <p class="foreward editor" v-html="editor" />
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

  data() {
    return {
      tabSelected: 'foreward'
    }
  },

  computed: {
    bio () { return copy.bio},
    contact () { return copy.contact },
    foreward () { return copy.foreward.en },
    editor () { return copy.foreward.editor }
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
  position: relative;
  padding-top: 2rem;
  padding-right: 2rem;
  overflow-y: auto;
  @include scrollbars(10px, transparent, transparent);
  &:hover {
    @include scrollbars(10px, $green, $light);
    scrollbar {
      z-index: 10;
    }
  }
  @include tablet {
    padding: 0 1rem;
  }
}

.left-title {
  margin: 2rem 0;
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

.tabs {
  z-index: 1;
  position: relative;
  display: flex;
  &::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: calc(100% + 3rem);
    background-image: linear-gradient($light 60%, transparent 90%);
  }
  @include browser {
    padding-bottom: 1rem;
    &::after {
      height: calc(100% + 2rem);
    }
  }
  @include tablet {
    justify-content: center;
    padding-bottom: 1.5rem;
    &::after {
      display: none;
    }
  }
}

[class|=tab] {
  z-index: 2;
  padding: 0.5rem 1rem;
  background-color: rgba($yellow, .9);
  border-radius: 0.25rem;
  font-size: clamp(0.75rem, 1.3vw, 1rem);
  font-weight: 600;
  color: $light;
  transition: 150ms ease-in-out;
  &:not(:last-child) {
    margin-right: 0.5rem;
  }
  &:hover {
    background-color: rgba($blue, .9);
    cursor: pointer;
  }
  &.selected {
    background-color: rgba($green, .9);
  }
  @include tablet {
    font-size: clamp(0.75rem, 1.5vw, 1rem);
  }
}

.about-wrapper,
.foreward-wrapper {
  display: none;
  &.selected {
    display: block;
    width: 100%;
  }
}
.about-wrapper {
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

.foreward {
  font-size: clamp(1rem, 1.4vw, 1.3rem);
}

.editor {
  text-align: right;
}

</style>
