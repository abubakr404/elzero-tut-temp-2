<template>
  <div class="container">
    <a href="#" class="logo">
      <img src="../assets/images/logo.png" alt="logo" />
    </a>
    <nav>
      <button class="buger-button" @click="toggleMenu = !toggleMenu">
        <img
          src="../assets/images/icon-hamburger.svg"
          alt=""
          v-show="toggleMenu"
        />
        <img
          src="../assets/images/icon-close.svg"
          alt=""
          v-show="!toggleMenu"
        />
      </button>
      <div class="menu" :class="{ hide: toggleMenu }">
        <ul>
          <li
            v-for="(link, index) in links"
            :key="index"
            :class="{ active: link.isActive }"
          >
            <button @click="toggleActive(index)">
              <a :href="'#' + link.name">{{ link.name }}</a>
            </button>
          </li>
        </ul>
      </div>
      <div class="search">
        <form method="GET" v-show="toggleSearch">
          <input type="search" />
        </form>
        <button><i class="fa-solid fa-magnifying-glass"></i></button>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      toggleMenu: true,
      toggleSearch: false,
      links: [
        { name: "home", isActive: true },
        { name: "services", isActive: false },
        { name: "portfolio", isActive: false },
        { name: "about", isActive: false },
        { name: "pricing", isActive: false },
        { name: "contact", isActive: false },
      ],
    };
  },
  methods: {
    toggleActive: function (i) {
      this.links.forEach((link) => {
        link.isActive = false;
      });
      this.links[i].isActive = !this.links[i].isActive;
    },
  },
};
</script>
