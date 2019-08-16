<template>
  <toolbar>
    <div class="toolbar__info">
      <div class="container toolbar__info-container">
        <div class="toolbar__copyright">
          © {{ year }} — <span v-html="$t('toolbar.credits')"/>
        </div>
        <a href="#top" class="toolbar__top-page">
          ^
        </a>
      </div>
    </div>
  </toolbar>
</template>
<script>
export default {
  computed: {
    year () {
      return new Date().getFullYear()
    }
  }
}
</script>

<style lang="scss">
.toolbar {
	&__info {
		background-color: $background-secondary;//$background-primary;
        box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
		padding: 1.5em 0;
  }
  
  &__info-container {
    display: flex;
    justify-content: space-between;
    width: 100%;
    flex-direction: column;

    @media (min-width: $screen-sm){
      flex-direction: row;
    }
  }

	&__copyright {
		text-align: center;
		@media (min-width: $screen-sm) {
			text-align: inherit;
		}
	}

	&__top-page {
		color: $text-negative;
		display: block;
		text-align: center;
		line-height: 1;
		-webkit-transition: 1s;
		-moz-transition: 1s;
    transition: 1s;
    
		@media (min-width: $screen-sm){
			text-align: right;
		}
	}
}
</style>

