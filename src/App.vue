<template>
  <div id="app">
    <PageSidebar />

    <PageContent>
      <FlipBook />
    </PageContent>
  </div>
</template>

<script>
import PageSidebar from './components/PageSidebar'
import PageContent from './components/PageContent'
import FlipBook from './components/FlipBook'

export default {
  name: 'App',
  components: {
    PageSidebar,
    PageContent,
    FlipBook
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
}
</style>
