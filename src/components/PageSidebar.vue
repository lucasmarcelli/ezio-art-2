<template>
  <div class="sidebar">

    <div class="sidebar-container">
      <h1 class="sidebar-title">ezio marcelli</h1>

      <div class="sidebar-content">
        <img class="ezio-img" src="@/assets/cartoon-face.jpg" alt="this is his face"/>
        <p class="bio">
          Ezio Marcelli was born on February 17, 1954 in Colle- ferro (Rome) Italy. He attended the Liceo Artistico of Frosinone followed by the Academy of Fine Arts until being awarded a diploma in Painting in 1977. He moved to Canada in 1981 settling in Edmonton where he lived for 20 years working as a furniture draftsman. In 2002 he moved to Toronto, where he still lives, continuing his work as a furniture draftsman until 2019. After 42 years he took up painting once more; completing two canvases, Never Forgotten and Sadness, that he had brought unfinished from Italy. This marked the start of his producing newly inspired paintings which continues to this day.
        </p>
        <div class="contact">
          <p>
            Contact: ezio@marcelli.com
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PageSidebar'
}
</script>

<style lang="scss" scoped>

.sidebar {
  display: flex;
  flex-flow: column nowrap;
  justify-content: flex-start;
  width: 35%;
  @include tablet {
    width: 100%;
    margin-bottom: 10rem;
  }
}

.sidebar-title {
  font-family: 'Unbounded';
  font-weight: 400;
  font-size: 3.5rem;
}

.sidebar-content {
  @include tablet {
    margin-right: 8rem;
  }
}

.ezio-img {
  height: 4rem;
  float: left;
  margin-right: 1rem;
  object-fit: contain;
}

.bio {
  font-size: clamp(1.2rem, 1.4vw, 1.3rem);
  margin: 0;
}

.contact {
  font-size: 1rem;
}

// .background {
//   height: 100%;
//   width: 100%;
//   position: absolute;
//   top: 0;
//   left: 0;
//   .ribbon {
//     position: relative;
//     height: 100%;
//     width: 35%;
//     background: url(@/assets/ribbon.svg)0 0/ 100% 100% no-repeat ;
//     @include tablet {
//       transform: rotate(-90deg);
//       width: 85%;
//     }
//   }
// }

</style>
