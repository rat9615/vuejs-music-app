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
          class="cursor-pointer rounded-lg"
          >{{ item.html }}</slideritem
        >
      </slider>
    </div>
  </div>
</template>

<script>
import { slider, slideritem } from 'vue-concise-slider';

export default {
  name: 'Carousel',
  data() {
    return {
      someList: [
        {
          html: 'Hey - Afrojack',
          style: {
            background:
              "url('https://source.unsplash.com/user/@marcelalaskoski/YrtFlrLo2DQ')",
            backgroundSize: 'cover',
            width: '23.5%',
            marginRight: '0.5%',
          },
        },
        {
          html: 'slider2',
          style: {
            background: '#4bbfc3',
            width: '23.5%',
            marginRight: '0.5%',
          },
        },
        {
          html: 'slider3',
          style: {
            background: '#7baabe',
            width: '23.5%',
            marginRight: '0.5%',
          },
        },
        {
          html: 'slider4',
          style: {
            background: '#7caabe',
            width: '23.5%',
            marginRight: '0.5%',
          },
        },
        {
          html: 'slider5',
          style: {
            background: '#4abf8a',
            width: '23.5%',
            marginRight: '0.5%',
          },
        },
        {
          html: 'slider6',
          style: {
            background: '#4bbfc3',
            width: '23.5%',
            marginRight: '0.5%',
          },
        },
        {
          html: 'slider7',
          style: {
            background: '#7baabe',
            width: '23.5%',
            marginRight: '0.5%',
          },
        },
        {
          html: 'slider8',
          style: {
            background: '#7caabe',
            width: '23.5%',
            marginRight: '0.5%',
          },
        },
      ],
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
  },
};
</script>
