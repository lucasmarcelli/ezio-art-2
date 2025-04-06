<template>
  <div id="app">

    <PageLeft />

    <PageRight />

    <h1 class="title">
      ezio marcelli
    </h1>

  </div>
</template>

<script>
import PageLeft from './components/PageLeft'
import PageRight from './components/PageRight'

export default {
  name: 'App',

  components: {
    PageLeft,
    PageRight
  }
}
</script>

<style lang="scss">
@import url(@/assets/scss/index.scss);

#app {
  position: relative;
  padding: 0 3rem 0 5rem;
  display: flex;
  height: 100vh;
  @include browser {
    padding-left: 3rem;
  }
  @include tablet {
    padding: 2rem;
    height: 100%;
    width: calc(100% - 4rem);
    flex-direction: column-reverse;
    overflow-x: hidden;
  }
  @include mobile {
    padding: 1rem;
    width: calc(100% - 2rem);
  }
}

.title {
  display: none;
  @include tablet {
    display: block;
    @include siteTitle;
    text-align: center;
  }
  @include mobile {
    margin-bottom: 1.5rem;
  }
}

</style>
