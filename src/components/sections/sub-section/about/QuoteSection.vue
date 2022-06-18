<template>
  <section :class="heading.name" :id="heading.name">
    <div class="container">
      <q v-text="quote.text"></q>
      <p v-text="quote.author"></p>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      heading: { name: "quote", title: null, text: null },
      quote: {
        author: "John Doe",
        text: `ACCUMSAN ID CURABITUR ET PORTITOR MAURIS BLANDIT DOLOR LOREM SOME EST OUR DONEC STIN LORTIOS`,
      },
    };
  },
};
</script>
