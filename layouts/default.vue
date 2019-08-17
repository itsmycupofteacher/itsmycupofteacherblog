<template>
  <div class="layout">
    <NavBar/>
    <nuxt class="nuxt-content"/>
    <Footer/>
  </div>
</template>
<script>
  import Footer from '~/components/Sections/Footer'
  import NavBar from '~/components/Sections/NavBar'
  
  export default {
    components: {
      Footer,
      NavBar
    }
  }
</script>
<style lang="scss">
.layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.nuxt-content {
  flex-grow: 1;
}
</style>
