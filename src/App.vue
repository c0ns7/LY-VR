<template>
  <header class="header">
    <div class="wrapper">
      <div class="header-inner">
        <div class="logo">
          <a href="/">
            <img src="./assets/img/header/logo.svg" alt="">
            Zone.
          </a>
        </div>

        <div :class="{ menu: true, active: isActive }">
          <nav>
            <a href="#home">Home</a>
            <a href="#about">About Us</a>
            <a href="#service">Service</a>
            <a href="#pricing">Pricing</a>
            <a href="#blog">Blog</a>

            <a href="#contact" class="m-button">Contact Us</a>
          </nav>
        </div>

        <div class="menu-burger">
            <a href="#" class="b-button" @click="toggleMenu">
              <font-awesome-icon :icon="['fas', 'bars']" :class="{ open: !isMenuOpen, close: isMenuOpen }" />
              <font-awesome-icon :icon="['fas', 'xmark']" :class="{ open: isMenuOpen, close: !isMenuOpen }" />
            </a>
        </div>
      </div>
    </div>
  </header>

  <section class="top">
    <div class="wrapper">
      <div class="top-inner">
        <div class="t-block-left">
          <h1>Virtual Reality Business Solutions</h1>

          <p>We have over 15 year exprience in business consultting arena. We have over 15 year exprience in business consultting arena and artficial intelligence.</p>
        
          <div class="t-buttons">
            <nav>
              <a href="#join" class="join-us">Join Us</a>

              <a href="#watch-video">
                <img src="./assets/img/top/t-watch-btn.svg" alt="">
                Watch video
              </a>
            </nav>
          </div>
        </div>

        <div class="t-block-right">
          <img src="./assets/img/top/t-image.svg" alt="">
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const isActive = ref(false);
    const isMenuOpen = ref(false);

    const toggleMenu = () => {
      isActive.value = !isActive.value;
      isMenuOpen.value = !isMenuOpen.value;
      document.body.style.overflow = isActive.value ? 'hidden' : '';
    };

    return {
      isActive,
      isMenuOpen,
      toggleMenu
    };
  }
};
</script>
