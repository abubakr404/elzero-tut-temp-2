<template>
  <section :class="heading.name" :id="heading.name">
    <div class="container">
      <div class="stat" v-for="(statistic, index) in statistics" :key="index">
        <div class="icon" :style="`--icon: ${statistic.iconCode};`">
          <svg width="32" height="36" xmlns="http://www.w3.org/2000/svg">
            <polygon
              points="16,0 32,9 32,27 16,36 0,27 0,9"
              fill="#1f2021"
              stroke="#1f2021"
            ></polygon>
          </svg>
        </div>
        <h4 v-text="Number(statistic.number).toLocaleString()"></h4>
        <p v-text="statistic.title"></p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      heading: { name: "statistics", title: null, text: null },
      statistics: [
        { iconCode: "'\\f7b6'", number: 1263, title: "Coffee Drinks" },
        { iconCode: "'\\f07b'", number: 256, title: "Complated Projects" },
        { iconCode: "'\\f0e0'", number: 1743, title: "Mail Sent" },
        { iconCode: "'\\f559'", number: 17, title: "Awards Received" },
      ],
    };
  },
};
</script>
