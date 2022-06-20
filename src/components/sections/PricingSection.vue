<script setup>
import MainHeading from "./section-components/MainHeading.vue";
</script>

<template>
  <section :class="heading.name" :id="heading.name">
    <div class="container">
      <MainHeading>
        <template #title>{{ heading.title }}</template>
        <template #text>{{ heading.text }}</template>
      </MainHeading>
      <div class="plans">
        <div class="plan" v-for="(plan, index) in plans" :key="index">
          <div class="plan-head">
            <h3 v-text="plan.title"></h3>
            <span
              class="price"
              v-text="plan.offer.price"
              :data-currency="plan.offer.currency"
              :data-pre="plan.offer.pre"
            ></span>
          </div>
          <ul class="plan-features">
            <li
              v-for="(feature, index) in plan.features"
              :key="index"
              v-text="feature"
            ></li>
          </ul>
          <a :href="plan.link.url" v-text="plan.link.title"></a>
        </div>
      </div>
      <div class="contact">
        <p>Contact us if you have special request</p>
        <a href="#">Contact Us</a>
      </div>
    </div>
  </section>
  <section :class="subscribeSection.name" :id="subscribeSection.name">
    <div class="container">
      <form method="post" :style="`--icon: ${subscribeSection.iconCode};`">
        <input type="email" :placeholder="subscribeSection.placeholder" />
        <button type="submit" v-text="subscribeSection.buttonTitle"></button>
      </form>
      <p v-text="subscribeSection.text"></p>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      heading: {
        name: "pricing",
        title: "pricing",
        text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
      },
      plans: [
        {
          title: "basic",
          offer: { currency: "$", price: 19, pre: "/mo" },
          features: [
            "Feature NO 1",
            "Extra Feature",
            "Feature NO 2",
            "feature",
          ],
          link: { title: "Buy Now", url: "#" },
        },
        {
          title: "premium",
          offer: { currency: "$", price: 29, pre: "/mo" },
          features: [
            "Feature NO 1",
            "Extra Feature",
            "Feature NO 2",
            "feature",
          ],
          link: { title: "Buy Now", url: "#" },
        },
        {
          title: "pro",
          offer: { currency: "$", price: 39, pre: "/mo" },
          features: [
            "Feature NO 1",
            "Extra Feature",
            "Feature NO 2",
            "feature",
          ],
          link: { title: "Buy Now", url: "#" },
        },
        {
          title: "platinum",
          offer: { currency: "$", price: 49, pre: "/mo" },
          features: [
            "Feature NO 1",
            "Extra Feature",
            "Feature NO 2",
            "feature",
          ],
          link: { title: "Buy Now", url: "#" },
        },
      ],
      subscribeSection: {
        name: "subscribe",
        placeholder: "your mail",
        iconCode: "'\\f0e0'",
        buttonTitle: "Subscribe",
        text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
      },
    };
  },
};
</script>
