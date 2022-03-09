<template>
  <div class="container mt-3">
    <div class="card" style="width: 100%">
      <div class="card-body">
        <h5 class="card-title">Gif Router</h5>
        <h6 class="card-subtitle mb-2 text-muted">Testing project</h6>
        <p class="card-text" style="text-align: justify">
          This project is a test made with Vue 3 just to learn how to use the
          "Router" component in this version of Vue.
        </p>

        <router-link to="/gifs" class="card-link">Gifs</router-link>
        <router-link to="/stickers" class="card-link">Stickers</router-link>
      </div>
    </div>
  </div>
</template>