<template>
  <section :class="heading.name" :id="heading.name">
    <div class="images">
      <img src="../../assets/images/black-phone.png" alt="" />
      <img src="../../assets/images/white-phone.png" alt="" />
    </div>
    <div class="text">
      <h3 v-text="heading.title"></h3>
      <ul>
        <li
          v-for="(feature, index) in serviceFeatures"
          :key="index"
          :style="'--icon: ' + feature.iconCode + ';'"
          v-text="feature.text"
        ></li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      heading: {
        name: "desgin",
        title: "OUR DESIGNS COMES WITH...",
        text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
      },
      serviceFeatures: [
        { text: "Responsive Design", iconCode: "'\\f108'" },
        { text: "Modern And Clean Design", iconCode: "'\\f108'" },
        { text: "Clean Code", iconCode: "'\\f108'" },
        { text: "Browser Friendly", iconCode: "'\\f108'" },
      ],
    };
  },
};
</script>
