<template>
  <div class="header">

    <div class="container">
      <p class="logo text-title-2 -text-bold" @click="scrollToSection('hero')">Małgorzata Orzechowska</p>
      <div class="navigation" :class="{'navigation--open' : navOpen}">
        <div class="navigation__close" @click="navOpen = false">Close</div>
        <ul>
          <li @click="scrollToSection( 'about')">O mnie</li>
          <li @click="scrollToSection('psychotherapy')">O psychoterapii</li>
          <li @click="scrollToSection('reading__room')">Czytelnia</li>
          <li @click="scrollToSection('contact')">Kontakt</li>
        </ul>
      </div>
      <div class="header__actions">
        <button class="navigation__menu" @click="navOpen = true">Menu</button>
      </div>
    </div>
  </div>
</template>
<style>
.navigation__menu {
  font-family: var(--font-primary);
  font-size: var(--font-size-20);
  border: none;
  background: transparent;
  cursor: pointer;
}

.navigation__close {
  font-family: var(--font-primary);
  font-size: var(--font-size-20);
  display: none;
  @media screen and (max-width: 768px) {
    display: block;
    text-align: center;
    padding: 3.6rem;
    font-weight: bold;
  }
}

.header {
  padding: 0 3.2rem;
  position: fixed;
  width: 100%;
  display: flex;
  align-items: center;
  height: 10rem;
  opacity: 0;
  z-index: 100;
  transition: background-color 0.3s, color 0.3s, height 0.3s;
}

.header .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navigation.navigation--open {
  @media screen and (max-width: 768px) {
    opacity: 1;
    visibility: visible;
  }
}
.navigation {
  @media screen and (max-width: 768px) {
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 100vh;
    z-index: 99;
    background: var(--color-light);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.3s, visibility 0.3s;
  }
}

.navigation ul {
  display: flex;
  gap: 3.2rem;
  @media screen and (max-width: 768px) {
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 0;
  }
}

.navigation li {
  list-style: none;
  font-family: var(--font-secondary);
  font-size: var(--font-size-20);
  cursor: pointer;
  color: var(--color-light);
  @media screen and (max-width: 768px) {
    color: var(--color-dark);
    font-family: var(--font-primary);
    font-size: var(--font-size-48);
  }
}

.header--scrolled {
  background-color: var(--color-light);
  height: 5rem;
}

.header--scrolled .logo {
  @media screen and (max-width: 768px) {
    font-size: var(--font-size-16);
  }
}

.header--scrolled li {
  color: var(--color-dark);
}

.header--light {
  color: var(--color-light);
}

.logo {
  cursor: pointer;
  @media screen and (max-width: 768px) {
    flex: 1;
  }
}

.header__actions {
  display: none;
  @media screen and (max-width: 768px) {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
}
</style>
<script setup lang="ts">

const navOpen = ref(false);
const {$gsap} = useNuxtApp();

const scrollToSection = (section: string) => {
  const sectionElement = document.getElementById(section);
  $gsap.to(window, {duration: 1.5, scrollTo: sectionElement.offsetTop, ease: "expo.inOut"});
  navOpen.value = false;
}

onMounted(() => {
  $gsap.fromTo('.header', {
    opacity: 0,
    y: -10,
  }, {
    opacity: 1,
   y:0,
    duration: 1.5,
    ease: "expo.inOut",
  });
})

</script>