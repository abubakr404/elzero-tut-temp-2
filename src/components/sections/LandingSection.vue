<template>
  <section
    class="landing"
    id="home"
    :style="'background-image:url(/src/assets/images/' + activeImg.name + ')'"
  >
    <div class="text">
      <div class="content">
        <h2>
          HELLO WORLD! <br />
          WE ARE KASPER,WE MAKE ART.
        </h2>
        <p>
          Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
          Mauris blandit aliquet elit, eget tincidunt nibh pulvinar a. Curabitur
          aliquet quam. Accumsan id imperdiet et, porttitor at sem. Mauris
          blandit aliquet elit, eget tincidunt.
        </p>
      </div>
    </div>
    <button class="arrow" @click="activatePre">
      <i class="fa-solid fa-angle-left"></i>
    </button>
    <button class="arrow" @click="activateNext">
      <i class="fa-solid fa-angle-right"></i>
    </button>
    <ul class="bullet">
      <li
        v-for="(image, index) in images"
        :key="index"
        :class="{ active: image.id == activeImg.id }"
        @click="toggleActive(index)"
      ></li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      images: [
        { id: 0, name: "landing_1.jpg", isActive: false },
        { id: 1, name: "landing_2.jpg", isActive: false },
        { id: 2, name: "landing_3.jpg", isActive: false },
      ],
    };
  },
  computed: {
    activeImg: function () {
      let defaultImg = this.images[Math.ceil(this.images.length / 2) - 1];
      let filterImg;
      let activeImg;
      filterImg = this.images.filter((image) => image.isActive);
      activeImg = filterImg.length == 1 ? filterImg[0] : defaultImg;
      return activeImg;
    },
  },
  methods: {
    toggleActive: function (i) {
      this.images.forEach((image) => {
        image.isActive = false;
      });
      this.images[i].isActive = !this.images[i].isActive;
    },
    activateNext: function () {
      let newImg =
        this.activeImg.id < this.images.length - 1 ? this.activeImg.id + 1 : 0;
      this.images.forEach((image) => {
        image.isActive = false;
      });
      this.images[newImg].isActive = !this.images[newImg].isActive;
    },
    activatePre: function () {
      let newImg =
        this.activeImg.id > 0 ? this.activeImg.id - 1 : this.images.length - 1;
      this.images.forEach((image) => {
        image.isActive = false;
      });
      this.images[newImg].isActive = !this.images[newImg].isActive;
    },
  },
};
</script>
