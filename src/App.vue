<template>
  <div id="app">

    <PageSidebar />
    <!-- <BackgroundRibbon /> -->

    <PageContent>
      <ArtBook />
    </PageContent>

    <h1 class="title">
      ezio marcelli
    </h1>

  </div>
</template>

<script>
import PageSidebar from './components/PageSidebar'
import PageContent from './components/PageContent'
import ArtBook from './components/ArtBook'
// import BackgroundRibbon from '@/components/BackgroundRibbon'

export default {
  name: 'App',

  components: {
    PageSidebar,
    PageContent,
    ArtBook
    // BackgroundRibbon
  }
}
</script>

<style lang="scss">
@import url(@/assets/scss/index.scss);

#app {
  padding: 2.5rem 3rem 0 7rem;
  display: flex;
  height: calc(100vh - 3rem);
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
  @include mobile {
    display: block;
    @include siteTitle;
  }
}

</style>
