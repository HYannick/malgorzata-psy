<template>
  <section id="psychotherapy" class="psychotherapy">
    <div class="container">
      <div class="psychotherapy__content">
        <div class="psychotherapy__heading">
          <div data-animate="psychotherapy-title" class="psychotherapy__heading-title ov-hidden">
            <h2 class="text-display">O psychoterapii</h2>
          </div>
          <div data-animate="psychotherapy-subtitle" class="psychotherapy__heading-subtitle ov-hidden">
            <span class="text-paragraph-3 -text-light">DEFINICJA, PROCES I REALIZACJA</span>
          </div>
          <div class="divider"></div>
        </div>
        <div data-animate="psychotherapy-content" class="psychotherapy__content-text ov-hidden">
          <p class="text-paragraph-2">
            Oficjalna definicja mówi, że „psychoterapia jest świadomym i zamierzonym zastosowaniem metod klinicznych i oddziaływań interpersonalnych
            pochodzących z uznanych zasad psychologicznych w celu towarzyszenia ludziom w zmianie ich zachowań, procesów poznawczych, emocji i/lub
            innych
            cech osobowych w kierunku, który korzystający z psychoterapii uważają za pożądany.” Mówiąc prościej to spotkanie terapeuty i
            klienta/pacjenta
            zmierzające do zmiany przeżywania, myślenia i zachowania ukierunkowane na usunięcie uciążliwych objawów i ich przyczyn...
          </p>
        </div>
        <div data-animate="psychotherapy-actions" class="ov-hidden">
          <button class="button button__secondary -text-light">CZYTAJ DALEJ</button>
        </div>
      </div>
      <div class="psychotherapy__picture">
        <img
            src="https://images.unsplash.com/photo-1434030216411-0b793f4b4173?q=80&w=3540&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            alt="psycho"/>
      </div>
    </div>

  </section>
</template>
<style>

.psychotherapy {
  text-align: left;
  background-color: var(--color-primary);
  color: var(--color-light);
  min-height: 100vh;
  display: flex;
  padding: 12.8rem 3.2rem;
  @media screen and (max-width: 768px) {

    text-align: center;
  }
}

.psychotherapy__content-text {
  margin: 6.4rem 0;
  @media screen and (max-width: 768px) {
    margin: 3.2rem 0;
  }
}

.psychotherapy .container {
  display: flex;
  justify-content: space-between;
  gap: 12.8rem;
  @media screen and (max-width: 768px) {
    flex-direction: column;
    gap: 3.6rem;
  }
}

.psychotherapy .divider {
  margin: 0;
  @media screen and (max-width: 768px) {
    margin: 0 auto;
  }
}

.psychotherapy__heading h2 {
  line-height: 1.3;
}

.psychotherapy__heading span {
  display: block;

}
.psychotherapy__heading .psychotherapy__heading-title {
  margin-bottom: 3.6rem;
}
.psychotherapy__heading .psychotherapy__heading-subtitle {
  margin-bottom: 3.6rem;
}
.psychotherapy__picture {
  flex: 1;
  overflow: hidden;
  border-radius: 1.5rem;
  @media screen and (max-width: 768px) {
    order: 1;
  }
}

.psychotherapy__picture img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 1.5rem;
}

.psychotherapy__content {
  flex: 1;
  @media screen and (max-width: 768px) {
    order: 2;
  }
}
</style>
<script setup lang="ts">
import {VERTICAL_TRANSLATION} from '~/src/common/animation.constants';

const {$gsap} = useNuxtApp();
onMounted(() => {


  const tl = $gsap.timeline({
    scrollTrigger: {
      trigger: ".psychotherapy",
      start: 'top 80%',
    }
  });

  tl
      .from('.psychotherapy__picture img', {
        opacity: 0,
        scale: 1.1,
        duration: 2,
        ease: "expo.inOut",
      }, '-=0.5')
      .from('[data-animate="psychotherapy-title"] h2', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 1.5,
        ease: "expo.inOut",
      }, '-=1.5')
      .from('[data-animate="psychotherapy-subtitle"] span', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 1.5,
        ease: "expo.inOut",
      }, '-=1.5')
      .from('.psychotherapy .divider', {
        opacity: 1,
        scaleX: 0,
        transformOrigin: 'left',
        duration: 1.5,
        ease: "expo.inOut",
      }, '-=1.5')
      .from('[data-animate="psychotherapy-content"] p ', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 2,
        ease: "expo.inOut",
      }, '-=1.6')
      .from('[data-animate="psychotherapy-actions"] button ', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 2,
        ease: "expo.inOut",
      }, '-=1.8');

})
</script>