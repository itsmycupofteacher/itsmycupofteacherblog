<template>
  <div class="layout">
    <ToolBar/>
    <nuxt class="nuxt-content"/>
    <Footer/>
  </div>
</template>
<script>
  import Footer from '~/components/Sections/Footer'
  import ToolBar from '~/components/Sections/ToolBar'
  
  export default {
    components: {
      Footer,
      ToolBar
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
