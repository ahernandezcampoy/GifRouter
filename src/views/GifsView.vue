<template>
  <div class="container mt-3 border">
    <h1 class="text-center">Gifs view</h1>
    <search @action="getGifs" />
    <hr />
    <loading v-if="isLoading"/>
    <div class="row">
      <div class="col-12 col-lg-3" v-for="gif in gifs" :key="gif.id">
        <gif-card :data="gif" class="m-3 w-75" />
      </div>
    </div>
  </div>
</template>

<script>
import Loading from '../components/Loading.vue';
import GifCard from "../components/GifCard.vue";
import Search from "../components/Search.vue";

export default {
  components: {
    GifCard,
    Search,
    Loading,
  },

  data: () => ({
    gifs: null,
    isLoading: false
  }),

  created() {
    this.getGifs();
  },

  methods: {
    async getGifs(search = "lol") {
      this.isLoading = true;
      const { data } = await this.axios.get(
        `https://api.giphy.com/v1/gifs/search?api_key=wmeO0nlZ4oAy2iw1VbA0xd9AHGpQ14Ge&q=${search}`
      );
      this.gifs = data.data;
      this.isLoading = false;
    },
  },
};
</script>
