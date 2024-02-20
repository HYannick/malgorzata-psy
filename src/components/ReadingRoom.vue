<template>
  <section id="reading__room" class="reading__room">
    <img class="flower__background flower__background-bottom" src="~/assets/svg/flower.svg" alt="flower-background"/>
    <img class="flower__background flower__background-top" src="~/assets/svg/flower.svg" alt="flower-background"/>
    <div class="container">
      <div class="reading__room-title">
        <h2 class="text-display">Czytelnia</h2>
      </div>
      <div class="reading__room-content">
        <p class="text-paragraph-2">Zapraszam Cię do zgłębiania fascynującego świata psychologii poprzez inspirujące cytaty, które rzucają światło na
          głębokie aspekty ludzkiego
          umysłu i zachowań. Odkryj mądrość wielkich myślicieli z dziedziny psychologii, którzy ukazują istotne prawdy o naturze ludzkiej psychiki.
          Znajdziesz tu zbiór myślowych pereł, które nie tylko zaintrygują, lecz również skłonią do refleksji nad własnymi doświadczeniami i relacjami
          interpersonalnymi.</p>
      </div>
      <div class="reading__room-actions">
        <button class="button button__primary -text-light">PRZEJDŹ DO CZYTELNI</button>
      </div>
    </div>
  </section>
</template>
<style>
.reading__room .flower__background-bottom {
  top: -10rem;
  left: -10rem;
  @media screen and (max-width: 768px) {
    left: 0;
  }
}
.reading__room .flower__background-top {
  bottom: -10rem;
  right: -10rem;
  @media screen and (max-width: 768px) {
    left: 0;
  }
}
.reading__room {
  padding: 3.2rem;
  color: var(--color-primary);
}

.reading__room .reading__room-title {
  margin-top: 12.8rem;
  margin-bottom: 6.4rem;
  line-height: 1.3;
  text-align: center;
  overflow: hidden;
}


.reading__room .reading__room-content {
  max-width: 70rem;
  text-align: center;
  margin: 0 auto;
}
.reading__room-actions {
  overflow: hidden;
}
.reading__room .button {
  display: block;
  margin: 6.4rem auto;
}

</style>
<script setup lang="ts">
import {VERTICAL_TRANSLATION} from '~/src/common/animation.constants';

const {$gsap} = useNuxtApp();
onMounted(() => {
  const mm = $gsap.matchMedia();

  mm.add("(min-width: 800px)", () => {
    const tl = $gsap.timeline({
      scrollTrigger: {
        trigger: ".reading__room",
        start: 'top 80%',
      }
    });

    tl
        .from('.reading__room-title h2', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 1.5,
          ease: "expo.inOut",
        }, '-=0.3')
        .from('.reading__room-content p ', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 2,
          ease: "expo.inOut",
        }, '-=1.6')
        .from('.reading__room-actions button ', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 2,
          ease: "expo.inOut",
        }, '-=1.8');
  });

})
</script>