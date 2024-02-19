<template>
  <section id="reading__room" class="reading__room">
    <img class="flower__background flower__background-bottom" src="~/assets/svg/flower.svg" alt="flower-background"/>
    <img class="flower__background flower__background-top" src="~/assets/svg/flower.svg" alt="flower-background"/>
    <div class="container">
      <h2 class="about__title text-display">Czytelnia</h2>
      <p class="text-paragraph-2">Zapraszam Cię do zgłębiania fascynującego świata psychologii poprzez inspirujące cytaty, które rzucają światło na
        głębokie aspekty ludzkiego
        umysłu i zachowań. Odkryj mądrość wielkich myślicieli z dziedziny psychologii, którzy ukazują istotne prawdy o naturze ludzkiej psychiki.
        Znajdziesz tu zbiór myślowych pereł, które nie tylko zaintrygują, lecz również skłonią do refleksji nad własnymi doświadczeniami i relacjami
        interpersonalnymi.</p>
      <button class="button button__primary -text-light">PRZEJDŹ DO CZYTELNI</button>
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

.reading__room .about__title {
  margin-top: 12.8rem;
  margin-bottom: 6.4rem;
}

.reading__room p {
  max-width: 70rem;
  text-align: center;
  margin: 0 auto;
}

.reading__room .button {
  display: block;
  margin: 6.4rem auto;
}

</style>