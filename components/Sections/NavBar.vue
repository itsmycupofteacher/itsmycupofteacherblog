<template>
  <div>
    <div class="toolbar__info">
      <div class="container toolbar__info-container">
        <div class="toolbar__name">
           <ImageResponsive
           :imageURL="'logo.svg'" />
        </div>
      </div>
    </div>
  </div>
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
		background-color: $background-primary;
		padding: 1.5em 0;
  }
  
  &__info-container {
    display: flex;
    justify-content: space-between;
    width: 100%;
    flex-direction: column;
  }

	&__name {
		display: block;
		text-align: center;
		line-height: 1;
		-webkit-transition: 1s;
		-moz-transition: 1s;
    transition: 1s;
	}
}
</style>

