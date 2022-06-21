<template>
  <section :class="heading.name" :id="heading.name">
    <video muted loop controls>
      <source src="../../../../assets/images/video.mp4" type="video/mp4" />
    </video>
    <div class="text">
      <h3 v-text="heading.title"></h3>
      <p v-text="heading.text"></p>
      <a href="#">See More</a>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      heading: {
        name: "video",
        title: "Super Awesome Vido Here",
        text: `It's All You Need`,
      },
    };
  },
};
</script>
