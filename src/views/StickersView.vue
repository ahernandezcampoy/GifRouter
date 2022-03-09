<template>
  <div class="container mt-3 border">
    <h1 class="text-center">Stickers view</h1>
    <search @action="getStickers" />
    <hr />
    <loading v-if="isLoading" />
    <div class="row">
      <div
        class="col-12 col-lg-3"
        v-for="sticker in stickers"
        :key="sticker.id"
      >
        <sticker-card :data="sticker" class="m-3 w-75" />
      </div>
    </div>
  </div>
</template>

<script>
import Loading from "../components/Loading.vue";
import StickerCard from "../components/StickerCard.vue";
import Search from "../components/Search.vue";

export default {
  components: {
    StickerCard,
    Search,
    Loading,
  },

  data: () => ({
    stickers: null,
    isLoading: false,
  }),

  created() {
    this.getStickers();
  },

  methods: {
    async getStickers(search = "lol") {
      this.isLoading = true;
      const { data } = await this.axios.get(
        `https://api.giphy.com/v1/stickers/search?api_key=wmeO0nlZ4oAy2iw1VbA0xd9AHGpQ14Ge&q=${search}`
      );
      this.stickers = data.data;
      this.isLoading = false;
    },
  },
};
</script>
