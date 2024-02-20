<template>
  <div>
    <Header/>
    <Hero/>
    <About/>
    <Psychotherapy/>
    <ReadingRoom/>
    <Contact/>
    <Footer/>
  </div>
</template>
<script setup lang="ts">
import Header from '~/src/components/Header.vue';
import Hero from '~/src/components/Hero.vue';
import About from '~/src/components/About.vue';
import Psychotherapy from '~/src/components/Psychotherapy.vue';
import ReadingRoom from '~/src/components/ReadingRoom.vue';
import Contact from '~/src/components/Contact.vue';
import Footer from '~/src/components/Footer.vue';

useHead({
  title: 'Małgorzata Orzechowska - Psychoterapia',
  meta: [
    {name: 'description', content: 'Psychoterapia'}
  ],
})
const {$gsap, $ScrollTrigger} = useNuxtApp();
onMounted(() => {
  $ScrollTrigger.create({
    start: 'top -70',
    end: 99999,
    toggleClass: {className: 'header--scrolled', targets: '.header'}
  });
})
</script>