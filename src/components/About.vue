<template>
  <section id="about" class="about">
    <div class="about__me">
      <div class="container">
        <div class="about__header">
          <div class="about__title ov-hidden">
            <h2 class="text-display">O mnie</h2>
          </div>
          <div class="about__subtitle ov-hidden">
            <span class="text-paragraph-3 -text-light">MAŁGORZATA ORZECHOWSKA</span>
          </div>

          <div class="divider"></div>
        </div>
        <div class="about__content ov-hidden">
          <p class="text-paragraph-2">Pewnie jesteś tu, bo szukasz pomocy dla siebie lub kogoś bliskiego. Może to Twój pierwszy kontakt z
            psychoterapią,
            a może kolejne podejście. Na tej stronie znajdziesz podstawowe informacje o mnie i mojej pracy. Dowiesz się czym jest a czym nie jest
            psychoterapia, w czym może Ci pomóc, ile trwa oraz czego spodziewać się po pierwszej konsultacji. W zakładce czytelnia znajdziesz też
            inspirujące treści i polecenia.</p>
        </div>
        <div class="about__action ov-hidden">
          <button class="button button__secondary -text-light">CZYTAJ DALEJ</button>
        </div>
      </div>
    </div>
    <div class="about__how">
      <img class="flower__background flower__background-bottom" src="~/assets/svg/flower.svg" alt="flower-background"/>
      <img class="flower__background flower__background-top" src="~/assets/svg/flower.svg" alt="flower-background"/>
      <div class="container">
        <div data-animate="about-how-title" class="ov-hidden">
          <h2 class="about__title text-display">W czym mogę Ci pomóc</h2>
        </div>
        <ul class="about__perks">
          <li><p class="text-paragraph-1">Przedłużające się doświadczenie smutku, zniechęcenia, braku sensu, radości i satysfakcji z życia</p></li>
          <li><p class="text-paragraph-1">Nerwica, depresja, myśli samobójcze</p></li>
          <li><p class="text-paragraph-1">Zaburzenia osobowości</p></li>
          <li><p class="text-paragraph-1">Doświadczanie silnego lęku</p></li>
          <li><p class="text-paragraph-1">Brak samoakceptacjii i niskie poczucie własnej wartości</p></li>
          <li><p class="text-paragraph-1">Poczucie, że życie cię przerasta, że nie radzisz sobie z tym, czego doświadczasz</p></li>
          <li><p class="text-paragraph-1">Poczucie, że inni ludzie Cię wykorzystują, a ty nie potrafisz się temu przeciwstawić</p></li>
          <li><p class="text-paragraph-1">Problem ze zbudowaniem trwałych i satysfakcjonujących relacji z innymi</p></li>
          <li><p class="text-paragraph-1">Nie radzisz sobie ze złością, agresją</p></li>
          <li><p class="text-paragraph-1">Doświadczenie przemocy lub uzależnienia w rodzinie</p></li>
          <li><p class="text-paragraph-1">Doświadczenie straty (śmierć bliskiej osoby, poronienie, rozstanie)</p></li>
          <li><p class="text-paragraph-1">Inne problemy których doświadczasz, razem poradzimy sobie ze wszystkim</p></li>
        </ul>
      </div>
    </div>
  </section>
</template>
<style>
.flower__background {
  position: absolute;
  z-index: -1;
  max-width: 57.5rem;
  width: 100%;
  object-fit: cover;
  @media screen and (max-width: 768px) {
    padding: 3.6rem;
  }
}

.about__how .flower__background-bottom {
  bottom: -10rem;
  left: -10rem;
  @media screen and (max-width: 768px) {
    left: 0;
  }
}

.about__how .flower__background-top {
  top: -10rem;
  right: -10rem;
  @media screen and (max-width: 768px) {
    left: 0;
  }
}

.about__me {
  text-align: center;
  background-color: var(--color-primary);
  color: var(--color-light);
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 3.2rem;
  height: 80rem;
}

.about__perks {
  padding: 0;
  margin: 6.4rem auto 6.4rem;
  max-width: 110rem;
}

.about__perks li {
  margin-bottom: 3.2rem;
  overflow: hidden;
}

.about__how {
  padding: 3.2rem;
  color: var(--color-primary);
}

.about__how .about__title {
  margin-top: 12.8rem;
}

.divider {
  width: 12rem;
  margin: 0 auto;
  height: 0.1rem;
  background-color: var(--color-light);
}

.about__title {
  line-height: 1.3;
  text-align: center;
  overflow: hidden;
}

.about__header span {
  display: block;
}

.about__subtitle {
  margin-bottom: 3.6rem;
}

.about__content {
  max-width: 80rem;
  margin: 6.4rem auto;
}
</style>
<script setup lang="ts">
import {VERTICAL_TRANSLATION} from '~/src/common/animation.constants';

const {$gsap} = useNuxtApp();
onMounted(() => {


  const tl = $gsap.timeline({
    scrollTrigger: {
      trigger: ".about__me",
      start: 'top 80%',
    }
  });

  tl
      .from('.about__me h2', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 1.5,
        ease: "expo.inOut",
      }, '-=0.3')
      .from('.about__me span', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 1.5,
        ease: "expo.inOut",
      }, '-=1.5')
      .from('.about__me .divider', {
        opacity: 1,
        scaleX: 0,
        duration: 1.5,
        ease: "expo.inOut",
      }, '-=1.5')
      .from('.about__content p ', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 2,
        ease: "expo.inOut",
      }, '-=1.6')
      .from('.about__action button ', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 2,
        ease: "expo.inOut",
      }, '-=1.8');

  const tl2 = $gsap.timeline({
    scrollTrigger: {
      trigger: ".about__how",
      start: 'top 80%',
    }
  });

  tl2
      .from('[data-animate="about-how-title"] h2', {
        opacity: 0,
        y: VERTICAL_TRANSLATION,
        duration: 1.5,
        ease: "expo.inOut",
      }, '-=0.3')
      .from('.about__perks li p', {
        opacity: 0,
        y: 50,
        duration: 1,
        ease: "expo.inOut",
        stagger: 0.05,
      }, '-=1')

})
</script>