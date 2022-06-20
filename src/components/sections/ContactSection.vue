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
      <div class="content">
        <form method="post">
          <input type="text" :placeholder="placeholder.name" />
          <input type="email" :placeholder="placeholder.mail" />
          <textarea :placeholder="placeholder.message"></textarea>
          <button type="submit" v-text="buttonTitle"></button>
        </form>
        <div class="contact-ways">
          <div class="way">
            <h4>get in touch</h4>
            <p
              v-for="(phone, index) in contact.phones"
              :key="index"
              v-text="phone"
            ></p>
          </div>
          <div class="way">
            <h4>where we are</h4>
            <p
              v-if="contact.address.street != null"
              v-text="contact.address.street"
            ></p>
            <p
              v-if="contact.address.city != null"
              v-text="contact.address.city"
            ></p>
            <p
              v-if="contact.address.phone != null"
              v-text="contact.address.phone"
            ></p>
            <p
              v-if="contact.address.country != null"
              v-text="contact.address.country"
            ></p>
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
      heading: {
        name: "contact",
        title: "Contact Us",
        text: `Curabitur arcu erat, accumsan id imperdiet et, porttitor at sem.
        Mauris blandit aliquet elit, eget tincidunt.`,
      },
      placeholder: {
        name: "your name",
        mail: "your mail",
        message: "your message",
      },
      buttonTitle: "send message",
      contact: {
        phones: ["+00 123 456 789", "+00 123 456 789"],
        address: {
          street: "Awesome Address 17",
          city: "New York,NYC",
          phone: "123-4567-890",
          country: "USA",
        },
      },
    };
  },
};
</script>
