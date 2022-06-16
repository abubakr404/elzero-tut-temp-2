<template>
  <section :class="heading.name" :id="heading.name">
    <video autoplay muted loop>
      <source src="../../assets/images/place-holder.mov" />
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
