<template>
  <div v-show="value">
    <div class="opacity-25 fixed inset-0 z-40 bg-black" @click.prevent="close"></div>
  </div>
</template>

<script>
export default {
  name: "MusicPlayer",
  props: {
    value: {
      required: true,
    },
  },
  methods: {
    close() {
      this.$emit("input", !this.value);
    },
  },
};
</script>
