<template>
  <section class="desgin" id="desgin">
    <div class="images">
      <img src="../../assets/images/black-phone.png" alt="" />
      <img src="../../assets/images/white-phone.png" alt="" />
    </div>
    <div class="text">
      <h3 v-text="serviceFeature.title"></h3>
      <ul>
        <li
          v-for="(feature, index) in serviceFeature.features"
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
      serviceFeature: {
        title: "OUR DESIGNS COMES WITH...",
        features: [
          { text: "Responsive Design", iconCode: "'\\f108'" },
          { text: "Modern And Clean Design", iconCode: "'\\f108'" },
          { text: "Clean Code", iconCode: "'\\f108'" },
          { text: "Browser Friendly", iconCode: "'\\f108'" },
        ],
      },
    };
  },
};
</script>
