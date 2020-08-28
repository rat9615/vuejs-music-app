<template>
  <div v-show="value">
    <div class="opacity-25 fixed inset-0 z-40 bg-black" @click="close"></div>
    <div
      class="overflow-x-hidden overflow-y-auto fixed inset-0 z-50 outline-none focus:outline-none justify-center items-center flex"
    >
      <div class="relative w-auto my-6 mx-auto max-w-6xl">
        <div
          class="border-0 rounded-lg shadow-lg relative flex flex-col w-full bg-gray-800 outline-none focus:outline-none"
        >
          <div class="flex items-start justify-between p-3 border-gray-300 rounded-t">
            <button
              class="p-1 ml-auto bg-transparent border-0 text-gray-300 opacity-5 float-right text-3xl leading-none font-semibold outline-none focus:outline-none"
              @click="close"
            >
              <span
                class="bg-transparent text-gray-300 opacity-5 h-6 w-6 text-2xl block outline-none focus:outline-none"
              >×</span>
            </button>
          </div>
          <div class="p-6 pb-8 flex flex-row justify-between text-white">
            <div class="px-8 flex items-center">
              <button v-if="!isPlay" @click="play" class="h-24 w-24 border-none focus:border-none">
                <svg
                  version="1.1"
                  id="Capa_1"
                  xmlns="http://www.w3.org/2000/svg"
                  xmlns:xlink="http://www.w3.org/1999/xlink"
                  x="0px"
                  y="0px"
                  viewBox="0 0 320.001 320.001"
                  style="enable-background:new 0 0 320.001 320.001;"
                  xml:space="preserve"
                  class="fill-current"
                >
                  <path
                    d="M295.84,146.049l-256-144c-4.96-2.784-11.008-2.72-15.904,0.128C19.008,5.057,16,10.305,16,16.001v288
	c0,5.696,3.008,10.944,7.936,13.824c2.496,1.44,5.28,2.176,8.064,2.176c2.688,0,5.408-0.672,7.84-2.048l256-144
	c5.024-2.848,8.16-8.16,8.16-13.952S300.864,148.897,295.84,146.049z"
                  />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                </svg>
              </button>
              <button v-else @click="pause" class="h-24 w-24">
                <svg
                  version="1.1"
                  id="Capa_1"
                  xmlns="http://www.w3.org/2000/svg"
                  xmlns:xlink="http://www.w3.org/1999/xlink"
                  x="0px"
                  y="0px"
                  viewBox="0 0 477.867 477.867"
                  style="enable-background:new 0 0 477.867 477.867;"
                  xml:space="preserve"
                  class="fill-current"
                >
                  <g>
                    <g>
                      <path
                        d="M187.733,0H51.2c-9.426,0-17.067,7.641-17.067,17.067V460.8c0,9.426,7.641,17.067,17.067,17.067h136.533
			c9.426,0,17.067-7.641,17.067-17.067V17.067C204.8,7.641,197.159,0,187.733,0z"
                      />
                    </g>
                  </g>
                  <g>
                    <g>
                      <path
                        d="M426.667,0H290.133c-9.426,0-17.067,7.641-17.067,17.067V460.8c0,9.426,7.641,17.067,17.067,17.067h136.533
			c9.426,0,17.067-7.641,17.067-17.067V17.067C443.733,7.641,436.092,0,426.667,0z"
                      />
                    </g>
                  </g>
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                  <g />
                </svg>
              </button>
            </div>
            <div>
              <h1 class="text-semibold text-5xl px-6">Hey - Afrojack</h1>
            </div>
          </div>
        </div>
      </div>
    </div>
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
      this.player.pause();
      this.player.src = "";
      this.isPlay = false;
    },
    play() {
      if (typeof src == "undefined") {
        this.player.src = this.src;
      }
      this.player.play();
      this.player.addEventListener(
        "ended",
        function () {
          this.isPlay = false;
          this.$emit("input", !this.value);
        }.bind(this)
      );
      this.isPlay = true;
    },
    pause() {
      this.player.pause();
      this.isPlay = false;
    },
  },
  data() {
    return {
      isPlay: false,
      src: require("../assets/fais_afrojack_hey.mp3"),
      player: new Audio(),
    };
  },
};
</script>
