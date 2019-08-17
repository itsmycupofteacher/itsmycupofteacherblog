<template>
  <section>
    <div id="app-search">
      <div class="search-wrapper">
        <input type="text" v-model="searchText" :placeholder="$t('blogSection.search')" />
      </div>
    </div>
    <div class="blogs__top">
      <div>
        <h2>{{ $t('posts') }}</h2>
        <span class="emoji-title emoji--writing" />
      </div>
      <LangSwitcher />
    </div>
    <ul class="blogs">
      <blog-card v-for="blog in filteredList" :key="blog.name" :blog="blog" />
    </ul>
  </section>
</template>f
<script>
import BlogCard from "~/components/BlogCard.vue";
import LangSwitcher from "~/components/LangSwitcher";

export default {
  components: { BlogCard, LangSwitcher },
  data() {
    return {
      searchText: "",
    };
  },
  computed:{
    getSearch() {
      return this.searchText;
    },
    firstPost() {
      return this.blogs[0].name;
    },
   filteredList() {
      return this.blogs.filter(blog => {
        return blog.title.toLowerCase().includes(this.getSearch.toLowerCase()) || 
        blog.descriptio.toLowerCase().includes(this.getSearch.toLowerCase())
      })
    }
  },
  props: {
    blogs: {
      type: Array
    }
  }
};
</script>
<style lang="scss">
.blogs {
  margin: 0;

  @media (min-width: $screen-sm) {
    grid-template-columns: 1fr 1fr;
    grid-gap: 50px;
    display: grid;
  }

  &__top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-top: 4rem;
  }
}

div#app-search {
  display: flex;
  align-items: right;
  justify-content: right;

  .search-wrapper {
    position: relative;
    margin-top: 30px;
    width: 100%;

    input {
      width: 90%;
      padding: 10px 12px;
      outline: 4px dashed $secondary;
      border: none;
      background: white;
      + label {
        display: none;
      }
      &:focus {
        outline: 4px dashed $primary;
      }
      &::-webkit-input-placeholder {
        font-size: 15px;
        color: rgba(0, 0, 0, 0.5);
        font-weight: 100;
      }
    }
  }

  .wrapper {
    display: flex;
    flex-wrap: wrap;
    padding-top: 12px;
  }
}
</style>

