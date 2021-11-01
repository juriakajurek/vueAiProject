<template>
  <div class="navbar" :class="{ 'navbar--hidden': !showNavbar }">
    <div class="bg"></div>
    <div class="logo">
      <router-link to="/">
        <img class="logo-image" src="../assets/logo.png" />
        <h1>Portfolio nieruchomości</h1>
      </router-link>
    </div>
    <div class="nav-buttons">
      <Button text="Logowanie" @button-click="loginButtonClicked()" />
      <Button text="Rejestracja" @button-click="signinButtonClicked()" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Button from "@/components/Button.vue";

import router from "../router";

export default {
  name: "Navbar",
  components: {
    Button,
  },
  data() {
    return {
      showNavbar: true,
      lastScrollPosition: 0,
    };
  },
  methods: {
    loginButtonClicked() {
      router.push("login");
    },
    signinButtonClicked() {
      router.push("signin");
    },
    onScroll() {
      const currentScrollPosition =
        window.pageYOffset || document.documentElement.scrollTop;
      if (currentScrollPosition < 0) {
        return;
      }
      // Stop executing this function if the difference between
      // current scroll position and last scroll position is less than some offset
      if (Math.abs(currentScrollPosition - this.lastScrollPosition) < 50) {
        return;
      }
      this.showNavbar = currentScrollPosition < this.lastScrollPosition;
      this.lastScrollPosition = currentScrollPosition;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.onScroll);
  },
};
</script>


<style scoped lang="less">
a,
a:visited,
a:active,
a:link,
a:hover {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  color: inherit;
}
.navbar {
  .bg {
    width: 120%;
    height: 100%;
    background-color: rgba(#cfe5d0, 0.15);
    position: absolute;
    z-index: -12;
    left: -4rem;
  }
  margin-top: 1rem;
  position: fixed;
  z-index: 100;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;

  padding-left: 4rem;
  padding-right: 4rem;

  height: 4rem;
  width: calc(100vw - 8rem);

  background-color: white;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
  transition: all 0.4s ease;
}
.navbar.navbar--hidden {
  box-shadow: none;
  transform: translate3d(0, -130%, 0);
  transition: all 0.4s ease;
}
/* image 16 */
.logo {
  width: auto;
  height: 32px;

  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  h1 {
    padding-top: 0.5rem;
    padding-left: 0.5rem;
    // color: #8a978a;
    font-size: 1.3rem;
    font-weight: 800;

    background-color: #8a978a;
    color: transparent;
    text-shadow: 2px 2px 3px rgba(255, 255, 255, 0.1);
    -webkit-background-clip: text;
    -moz-background-clip: text;
    background-clip: text;
  }
  .logo-image {
    width: 32px;
    height: 32px;
    opacity: 0.4;

    background: url(../assets/logo.png);
  }
}
</style>