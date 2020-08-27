<template>
  <div id="app" class="bg-gray-900 h-screen flex flex-col">
    <Header />
    <Carousel />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Carousel from "./components/Carousel.vue";

export default {
  name: "App",
  components: {
    Header,
    Carousel,
  },
};
</script>