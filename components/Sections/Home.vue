<template>
  <div>
    <div class="home__info">
      <div class="container home__info-container">
        <div class="home__init">
          <span v-html="$t('home.credits')"/>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  computed: {
    year() {
      return new Date().getFullYear();
    }
  }
};
</script>

<style lang="scss">
.home {
  &__info {
    background-color: $background-secondary;
    padding: 1.5em 0;
  }

  &__info-container {
    display: flex;
    justify-content: space-between;
    width: 100%;
    flex-direction: column;
  }

  &__init {
    color: $text-negative;
    display: block;
    text-align: center;
    line-height: 1;
    -webkit-transition: 1s;
    -moz-transition: 1s;
    transition: 1s;
  }
}
</style>

