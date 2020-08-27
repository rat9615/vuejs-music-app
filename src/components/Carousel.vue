<template>
  <div class="flex flex-col pl-16 pt-16 text-gray-300 font-extrabold">
    <h1 class="text-3xl mb-6">My Playlist</h1>
    <div class="w-full h-64 font-semibold">
      <slider
        ref="slider"
        :options="options"
        @slide="slide"
        @tap="onTap"
        @init="onInit"
      >
        <slideritem
          v-for="(item, index) in someList"
          :key="index"
          :style="item.style"
          class="cursor-pointer rounded-lg hover:shadow-lg transition duration-200 transform hover:-translate-y-2"
          v-on:click="handleClick"
          >{{ item.html }}</slideritem
        >
      </slider>
    </div>
    <MusicPlayer v-if="visible" />
  </div>
</template>

<script>
import { slider, slideritem } from 'vue-concise-slider';
import MusicPlayer from './MusicPlayer.vue';

export default {
  name: 'Carousel',
  data() {
    return {
      visible: false,
      someList: new Array(8).fill({
        html: 'Hey - Afrojack',
        style: {
          background:
            "url('https://source.unsplash.com/user/@marcelalaskoski/YrtFlrLo2DQ')",
          backgroundSize: 'cover',
          width: '23.5%',
          marginRight: '0.5%',
        },
      }),
      options: {
        currentPage: 0,
        tracking: false,
        thresholdDistance: 100,
        thresholdTime: 300,
        infinite: 4,
        slidesToScroll: 4,
        loop: true,
      },
    };
  },
  components: {
    slider,
    slideritem,
    MusicPlayer,
  },
  methods: {
    onTap: () => (this.visible = true),
  },
};
</script>
