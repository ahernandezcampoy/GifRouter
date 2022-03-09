<template>
  <div class="footer text-center bg-dark bg-gradient text-white py-2">
    <h3>&copy; {{ year }} - Alex Hernandez</h3>
  </div>
</template>

<script>
export default {
  data: () => ({
    year: new Date().getFullYear(),
  }),
};
</script>

<style>
.footer {
  position: fixed;
  bottom: 0;
  width: 100%;
}
</style>
