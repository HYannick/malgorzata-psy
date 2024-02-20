<template>
  <section id="hero" class="hero">
    <div class="hero__container container">
      <div class="hero__title ov-hidden">
        <p class="text-title-2"><span class="-text-bold">Gabinet Psychoterapii</span> & Rozwoju<br>Małgorzata Orzechowska</p>
      </div>
      <div class="hero__content">
        <div>
          <div class="hero__content-title ov-hidden">
            <h2 class="text-title-1 -text-bold">Porozmawiajmy.</h2>
          </div>
          <div class="hero__content-text ov-hidden">
            <p class="text-paragraph-1">Zaakceptuj siebie i przejmij odpowiedzialność za swoje życie, niezależnie od tego, co się w tym życiu
              wydarzyło.</p>
          </div>
        </div>
        <div class="hero__action ov-hidden">
          <button class="button button__primary -text-light" @click="scrollToSection('about')">O MNIE</button>
          <button class="button button__outline -text-light"  @click="scrollToSection('psychotherapy')">O PSYCHOTERAPII</button>
        </div>
      </div>
    </div>
    <div class="hero__image">
      <div class="waves">
        <img class="wave" src="~/assets/svg/wave.svg"/>
        <img class="wave" src="~/assets/svg/wave.svg"/>
        <img class="wave" src="~/assets/svg/wave.svg"/>
      </div>
      <img class="picture"
           src="https://images.pexels.com/photos/7176026/pexels-photo-7176026.jpeg"
           alt=""/>
    </div>
  </section>
</template>
<style>
.hero {
  padding: 12.8rem 3.2rem 3.2rem;
  position: relative;
  height: 100vh;
  opacity: 0;
  @media screen and (max-width: 768px) {
    height: initial;
    display: flex;
    flex-direction: column;
  }
}

.waves {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  z-index: 1;
  width: 30rem;

  @media screen and (max-width: 768px) {
    display: none;
  }
}

.waves img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.waves img:nth-child(1) {
  position: absolute;
  top: 0;
  left: 0;
}

.waves img:nth-child(2) {
  position: absolute;
  top: 0;
  left: 4rem;
  opacity: 0.7;
}

.waves img:nth-child(3) {
  position: absolute;
  top: 0;
  left: 8rem;
  opacity: 0.5;
}

.hero__image {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  overflow: hidden;
  max-width: 100rem;
  width: 100%;
  background-color: var(--color-dark);
  @media screen and (max-width: 1366px) {
    max-width: 50%;
  }
  @media screen and (max-width: 768px) {
    position: relative;
    max-width: 100%;
    height: 30rem;
    order: 1;
    overflow: hidden;
    border-radius: 1.5rem;
    margin-bottom: 3.6rem;
  }


}
.hero__title p {
  @media screen and (max-width: 768px) {
    text-align: center;
    font-size: var(--font-size-24);
  }
}
.hero__title span {
  @media screen and (max-width: 768px) {
    text-align: center;
    font-size: var(--font-size-32);
  }
}
.hero__content {
  text-align: left;
  @media screen and (max-width: 768px) {
    text-align: center;
  }
}
.hero__image .picture {
  height: 100%;
  object-fit: cover;
  opacity: 0.6;
}

.hero__container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 15rem;

  @media screen and (max-width: 768px) {
    order: 2;
    gap: 3.6rem;
  }
}

.hero__content {
  max-width: 51rem;
  @media screen and (max-width: 768px) {
    max-width: 100%;
  }
}

.hero__content-title {
  margin-bottom: 3.2rem;
}

.hero__action {
  margin-top: 6.4rem;
  display: flex;
  gap: 3.2rem;
  @media screen and (max-width: 768px) {
    flex-direction: column;
  }
}

.button {
  cursor: pointer;
  padding: 1.6rem 3.2rem;
  border-radius: 5rem;
  font-size: var(--font-size-20);
  font-family: var(--font-secondary);
  border: none;
}

.button.button__outline {
  background-color: var(--color-light);
  color: var(--color-primary);
  border: 0.1rem solid var(--color-primary);
}

.button.button__secondary {
  background-color: var(--color-light);
  color: var(--color-primary);
}

.button.button__primary {
  background-color: var(--color-primary);
  color: var(--color-light);
}
</style>
<script setup lang="ts">
import {VERTICAL_TRANSLATION} from '~/src/common/animation.constants';


const {$gsap} = useNuxtApp();

const scrollToSection = (section: string) => {
  const sectionElement = document.getElementById(section);
  $gsap.to(window, {duration: 1.5, scrollTo: sectionElement.offsetTop, ease: "expo.inOut"});
}
onMounted(() => {
  const tl = $gsap.timeline();
  tl.to('.hero', { opacity:1, duration: 2, ease: "expo.inOut"})
      .fromTo('.hero__image .picture', {scale: 1.1, opacity: 0}, {scale: 1, opacity: 0.6, duration: 5, ease: "expo.inOut"}, "-=3.5")
      .fromTo('.hero__title p', {y: VERTICAL_TRANSLATION, opacity: 0}, {y: 0, opacity: 1, duration: 3, ease: "expo.inOut"}, "-=3.6")
      .fromTo('.hero__content h2', {y: VERTICAL_TRANSLATION, opacity: 0}, {y: 0, opacity: 1, duration: 3, ease: "expo.inOut"}, "-=3.5")
      .fromTo('.hero__content p', {y: VERTICAL_TRANSLATION, opacity: 0}, {y: 0, opacity: 1, duration: 3, ease: "expo.inOut"}, "-=3.4")
      .fromTo('.hero__image .wave:nth-child(3)', {x: -100, opacity: 0}, {x: 0, opacity: 0.5, duration: 3, ease: "expo.inOut"}, "-=3.5")
      .fromTo('.hero__image .wave:nth-child(2)', {x: -100, opacity: 0}, {x: 0, opacity: 0.7, duration: 3, ease: "expo.inOut"}, "-=3.6")
      .fromTo('.hero__action button:nth-child(1)', {y: VERTICAL_TRANSLATION, opacity: 0}, {y: 0, opacity: 1, duration: 3, ease: "expo.inOut"}, "-=3.1")
      .fromTo('.hero__action button:nth-child(2)', {y: VERTICAL_TRANSLATION, opacity: 0}, {y: 0, opacity: 1, duration: 3, ease: "expo.inOut"}, "-=3")


})
</script>