<template>
  <div
    class="bg-gray-700 opacity-25 h-screen w-full flex flex-col items-center justify-center z-30"
    v-on:click="show = !show"
    v-if="show"
  >
    <h1>Hello world</h1>
  </div>
</template>

<script>
export default {
  name: 'MusicPlayer',
  data: function() {
    return {
      show: true,
    };
  },
};
</script>
