<template>
  <div class="app">
    <NavigationResponsive />
    <div class="home">
      <section class="hero">
        <div class="hero-text container">
          <h4>Vue Responsive Nav Menu</h4>
          <hr />
          <h2>
            With Vue <br />
            Animations
          </h2>
          <hr />
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import NavigationResponsive from "../src/components/NavigationResponsive.vue";
export default {
  name: "HomePage",
  components: { NavigationResponsive },
  data() {},
};
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100vw;
  margin: 0;
  min-width: 320px;
}
body {
  box-sizing: border-box;
  margin: 0;
}
.home {
  padding-top: 15vh;
  height: 85vh;
}
nav {
  padding: 30px;
  height: 15vh;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

.hero {
  background-image: url("./assets/hero-bg.png");
  background-attachment: fixed;
  position: relative;
  height: 100vh;
  padding-left: 50px;

  img {
    object-fit: cover;
    height: 100%;
    width: 100%;
  }

  .hero-text {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    color: #fff;

    h4 {
      text-transform: uppercase;
      font-size: 22px;
      padding-bottom: 4px;
    }

    h2 {
      font-size: 50px;
      @media (min-width: 550px) {
        font-size: 80px;
      }
    }

    hr:nth-child(2) {
      max-width: 365px;
      margin-bottom: 16px;
    }
    hr:nth-child(4) {
      height: 6px;
      background-color: #fff;
      border: none;
      max-width: 85px;
      margin-top: 16px;
    }
  }
}
</style>
