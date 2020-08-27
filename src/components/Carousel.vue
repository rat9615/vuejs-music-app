<template>
  <div class="flex flex-col pl-16 pt-16 text-gray-300 font-extrabold">
    <MusicPlayer v-if="showModal" />
    <h1 class="text-3xl mb-6">My Playlist</h1>
    <div class="w-full h-64 font-semibold">
      <slider ref="slider" :options="options" @tap="showModal = true">
        <slideritem
          v-for="(item, index) in someList"
          :key="index"
          :style="item.style"
          class="cursor-pointer rounded-lg hover:shadow-lg transition duration-200 transform hover:-translate-y-2"
          >{{ item.html }}</slideritem
        >
      </slider>
    </div>
  </div>
</template>

<script>
import { slider, slideritem } from 'vue-concise-slider';
import MusicPlayer from './MusicPlayer.vue';

export default {
  name: 'Carousel',
  data() {
    return {
      showModal: false,
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
};
</script>
