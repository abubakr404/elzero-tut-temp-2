<template>
  <section :class="heading.name" :id="heading.name">
    <div class="container">
      <div :class="sections[0].name">
        <div class="head">
          <h3 v-text="sections[0].title"></h3>
          <p v-text="sections[0].text"></p>
        </div>
        <div class="client" v-for="(client, index) in clients" :key="index">
          <img
            :src="`src/assets/images/${client.imgName}`"
            alt="client-avatar"
          />
          <div class="comment">
            <p v-text="client.comment"></p>
            <p v-text="client.name"></p>
          </div>
        </div>
        <ul class="bullet">
          <li></li>
          <li class="active"></li>
          <li></li>
        </ul>
      </div>
      <div :class="sections[1].name">
        <div class="head">
          <h3 v-text="sections[1].title"></h3>
          <p v-text="sections[1].text"></p>
        </div>
        <div class="content">
          <div class="skill" v-for="(skill, index) in skills" :key="index">
            <h4 v-text="skill.title"></h4>
            <div class="prog" :style="`--prog: ${skill.progress}%;`">
              <span
                :style="`margin-left: ${skill.progress}%;`"
                v-text="`${skill.progress}%`"
              ></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      heading: { name: "skills", title: null, text: null },
      sections: [
        {
          name: "testimonial",
          title: "testimonials",
          text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
        },
        {
          name: "our-skills",
          title: "Our Skills",
          text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
        },
      ],
      clients: [
        {
          name: "John Doe,CEO",
          imgName: "client (1).png",
          comment: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
          Mauris blandit aliquet elit, eget tincidunt.`,
        },
        {
          name: "John Doe,CEO",
          imgName: "client (2).png",
          comment: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
          Mauris blandit aliquet elit, eget tincidunt.`,
        },
      ],
      skills: [
        { title: "adobe", progress: 95 },
        { title: "html & css", progress: 93 },
        { title: "javascript", progress: 85 },
        { title: "php", progress: 87 },
      ],
    };
  },
};
</script>
