<template>
  <div id="app">
    <PageSidebar />

    <PageContent>
      <ArtBook />
    </PageContent>
  </div>
</template>

<script>
import PageSidebar from './components/PageSidebar'
import PageContent from './components/PageContent'
import ArtBook from './components/ArtBook'

export default {
  name: 'App',

  components: {
    PageSidebar,
    PageContent,
    ArtBook
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
}
</style>
