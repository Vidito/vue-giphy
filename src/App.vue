<template>
    <search-input @gifs-fetched="onGifsFetched"/>

    <gif-list :gifs="gifs"/>
</template>

<script>

import SearchInput from "./components/SearchInput.vue";
import GifList from "./components/GifList.vue";

export default {
  name: 'App',
  components: {
    GifList,
    SearchInput
  },
  data() {
    return {
      gifs: [],
    }
  },
  methods: {
    onGifsFetched(result) {
      console.log(result);
      this.gifs = result.data
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  padding: 20px;
  font-family: sans-serif;
  background: #f5f5f5;
}

#app {
  width: 800px;
  margin: 0 auto;
}
</style>