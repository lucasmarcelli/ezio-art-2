<template>
  <div class="sidebar">

    <div class="sidebar-container">
      <h1 class="sidebar-title">ezio marcelli</h1>

      <div class="sidebar-content">
        <img class="ezio-portrait" src="@/assets/ezio-marcelli.jpg" alt="this is his face"/>
        <p class="bio">
          Ezio Marcelli was born on February 17, 1954 in Colle- ferro (Rome) Italy. He attended the Liceo Artistico of Frosinone followed by the Academy of Fine Arts until being awarded a diploma in Painting in 1977. He moved to Canada in 1981 settling in Edmonton where he lived for 20 years working as a furniture draftsman. In 2002 he moved to Toronto, where he still lives, continuing his work as a furniture draftsman until 2019. After 42 years he took up painting once more; completing two canvases, Never Forgotten and Sadness, that he had brought unfinished from Italy. This marked the start of his producing newly inspired paintings which continues to this day.
        </p>
        <div class="contact">
          <p>
            Contact: ezio@marcelli.ca
          </p>
        </div>
      </div>
    </div>

    <!-- <BackgroundRibbon /> -->

  </div>
</template>

<script>
// import BackgroundRibbon from './BackgroundRibbon'

export default {
  name: 'PageSidebar',

  // components: {
  //   BackgroundRibbon
  // }
}
</script>

<style lang="scss" scoped>

.sidebar {
  display: flex;
  flex-flow: column nowrap;
  justify-content: flex-start;
  width: 35%;
  @include tablet {
    position: relative;
    width: 100%;
  }
  @include mobile {
    padding: 0;
  }
}

.sidebar-container {
  z-index: 10;
  @include tablet {
    padding: 1rem 9rem 3rem 1rem;
  }
  @include mobile {
    padding: 0 1rem;
  }
}

.sidebar-title {
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

.sidebar-content {
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

</style>
