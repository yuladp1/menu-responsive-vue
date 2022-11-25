<template>
  <header class="">
    <transition>
      <nav>
        <div class="branding">
          <img src="../assets/logo.png" alt="" />
        </div>
        <ul class="navigation" v-show="!mobile">
          <li class="link">Home</li>
          <li>About</li>
          <li class="link">Contacts</li>
          <li class="link">Portfolio</li>
        </ul>
        <div
          class="icon far fa-bars"
          v-on:click="toggleMobileNav"
          v-show="mobile"
          v-bind:class="{ 'icon-active': mobileNav }"
        ></div>
        <transition name="mobile-app">
          <ul class="dropdown-nav" v-show="mobileNav">
            <li class="link">Home</li>
            <li>About</li>
            <li class="link">Contacts</li>
            <li class="link">Portfolio</li>
          </ul>
        </transition>
      </nav>
    </transition>
  </header>
</template>

<script>
export default {
  name: "NavigationResponsive",
  components: {},

  data() {
    return {
      scrollPosition: null,
      mobile: false,
      mobileNav: null,
      windowWidth: null,
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 750) {
        this.mobile = true;
        return;
      } else {
        this.mobile = false;
        this.mobileNav = false;
        return;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: black;
  z-index: 99;
  width: 100%;
  height: 15vh;
  position: fixed;
  color: white;
}
nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 0;
  width: 90%;
  margin: 0 auto;
  @media (min-width: 1140px) {
    max-width: 1140px;
  }
}
ul {
  display: flex;
  gap: 10px;
}
li {
  font-weight: 500;
  color: white;
  text-transform: uppercase;
  list-style: none;
  font-size: 14px;
  padding-bottom: 4px;
  border-bottom: 1px solid transparent;
}
li:hover {
  color: rgb(73, 200, 250);
  border-color: rgb(235, 27, 165);
  transition: 0.5s ease-in-out all;
}
.icon {
  background-image: url("../assets/list.png");
  display: flex;
  width: 30px;
  height: 30px;
  background-size: cover;
  align-items: center;
}
.icon-active {
  transform: rotate(180deg);
}
.branding {
  display: flex;
  align-items: center;
  img {
    width: 50px;
  }
}
.dropdown-nav {
  margin: 0;
  display: flex;
  flex-direction: column;
  position: absolute;
  width: 120px;
  height: 100vh;
  background-color: white;

  top: 0;
  left: 0;
  padding: 10px 0 0 20px;
  li {
    color: black;
  }
}
</style>
