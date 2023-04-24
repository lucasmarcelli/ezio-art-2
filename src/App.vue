<template>
  <div id="app">

    <PageSidebar />
    <BackgroundRibbon />

    <PageContent>
      <ArtBook />
    </PageContent>
  </div>
</template>

<script>
import PageSidebar from './components/PageSidebar'
import PageContent from './components/PageContent'
import ArtBook from './components/ArtBook'
import BackgroundRibbon from '@/components/BackgroundRibbon'

export default {
  name: 'App',

  components: {
    PageSidebar,
    PageContent,
    ArtBook,
    BackgroundRibbon
  }
}
</script>

<style lang="scss">
@import url(@/assets/scss/index.scss);

#app {
  padding: 2.5rem 3rem 0 7rem;
  color: #2c3e50;
  display: flex;
  height: calc(100vh - 3rem);
}
</style>
