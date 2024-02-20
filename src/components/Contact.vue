<template>
  <section id="contact" class="contact">
    <div class="contact__infos">
      <div class="container">
        <div class="contact__heading">
          <h2 class="text-display">Kontakt</h2>
        </div>
        <div class="contact__blocs">
          <div class="contact__bloc">
            <div class="contact__bloc-title ov-hidden">
              <h3 class="text-paragraph-large -text-bold">GABINETY</h3>
            </div>
            <div class="contact__bloc-content ov-hidden">
              <p class="text-paragraph-2">Radzyń ul. Ostrowiecka 38<br>(Wejście z tyłu budynku od parkingu)</p>
              <br>
              <p class="text-paragraph-2">Łuków ul. Rogalińskiego 8</p>
            </div>
          </div>
          <div class="horizontal-divider"></div>
          <div class="contact__bloc">
            <div class="contact__bloc-title ov-hidden">
              <h3 class="text-paragraph-large -text-bold">Telefon</h3>
            </div>
            <div class="contact__bloc-content ov-hidden">
              <p class="text-paragraph-2">Zadzwoń, porozmawiajmy</p>
              <br>
              <p class="text-paragraph-2">+48 660 667 093</p>
            </div>
          </div>
          <div class="horizontal-divider"></div>
          <div class="contact__bloc">
            <div class="contact__bloc-title ov-hidden">
              <h3 class="text-paragraph-large -text-bold">E-mail</h3>
            </div>
            <div class="contact__bloc-content ov-hidden">
              <p class="text-paragraph-2">Napisz, pomogę</p>
              <br>
              <p class="text-paragraph-2">orzechowska.terapeuta@gmail.com</p>
            </div>
          </div>
        </div>
        <div data-animate="contact-more-infos" class="ov-hidden">
          <p class="text-paragraph-1">W wyjątkowych przypadkach istnieje również możliwość sesji online</p>
        </div>

      </div>
    </div>
    <div class="contact__appointment">
      <div class="container">
        <div class="contact__appointment-title ov-hidden">
          <h2 class="text-display">Zapraszam na spotkanie</h2>
        </div>
        <div class="contact__appointment-subtitle ov-hidden">
          <span class="text-paragraph-3 -text-light">MAŁGORZATA ORZECHOWSKA</span>
        </div>
        <div class="divider"></div>
        <div class="contact__appointment-actions">
          <a href="https://www.google.com/maps/place/Gabinet+Psychoterapii+Ma%C5%82gorzata+Orzechowska/@51.9250498,22.3736476,17.28z/data=!4m6!3m5!1s0x47220114fadc730f:0xb8552c9aea3c52ff!8m2!3d51.9250266!4d22.3778952!16s%2Fg%2F11qr5zfjx1?hl=en-US&entry=ttu"  target="_blank" class="button button__primary -text-light">ZNAJDŹ GABINET</a>
          <a href="mailto:orzechowska.terapeuta@gmail.com" class="button button__outline -text-light">WYŚLIJ MAIL’A</a>
        </div>
      </div>
    </div>
  </section>
</template>
<style>

.contact__infos {
  background-color: var(--color-primary);
  color: var(--color-light);
  padding: 12.8rem 3.2rem;
}

.contact__infos p {
  @media screen and (max-width: 768px) {
    text-align: center;
  }
}

.contact__content p {
  margin: 6.4rem 0;
}

.contact .container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.contact__heading {
  overflow: hidden;
  margin-bottom: 12.8rem;
}

.contact__heading h2 {
  line-height: 1.3;
}

.contact__appointment-subtitle span {
  display: block;
}

.contact__blocs {
  display: flex;
  margin: 0 auto 6.4rem;
  width: 100%;
  @media screen and (max-width: 768px) {
    flex-direction: column;
  }
}

.contact__blocs > .contact__bloc {
  flex: 1;
  text-align: center;
}

.contact__bloc-title {
  margin-bottom: 3.2rem;
}

.contact__blocs h3 {
  letter-spacing: 0.5rem;
  text-transform: uppercase;
}

.horizontal-divider {
  width: 0.1rem;
  height: 20rem;
  background-color: var(--color-light);
  margin: 0 6.4rem;
  @media screen and (max-width: 768px) {
    width: 10rem;
    height: 0.1rem;
    margin: 6.4rem auto;
  }
}

.contact__appointment {
  padding: 12.8rem 3.2rem;
  color: var(--color-primary);
  background-color: var(--color-light);
  text-align: center;
}

.contact__appointment span {
  display: block;
  margin: 1.2rem auto 3.2rem;
}

.contact__appointment .divider {
  background-color: var(--color-primary);
}

.contact__appointment-actions {
  display: flex;
  gap: 3.2rem;
  margin: 6.4rem auto;
  overflow: hidden;
  @media screen and (max-width: 768px) {
    flex-direction: column;
  }
}
</style>
<script setup lang="ts">
import {VERTICAL_TRANSLATION} from '~/src/common/animation.constants';

const {$gsap} = useNuxtApp();
onMounted(() => {
  let mm = $gsap.matchMedia();

  mm.add("(min-width: 800px)", () => {

    const tl = $gsap.timeline({
      scrollTrigger: {
        trigger: ".contact",
        start: 'top 80%',
      }
    });

    tl
        .from('.contact__heading h2', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 1.5,
          ease: "expo.inOut",
        }, '-=0.3')
        .from('.contact__heading-content p ', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 2,
          ease: "expo.inOut",
        }, '-=1.6')
        .from('.horizontal-divider', {
          opacity: 1,
          scaleY: 0,
          duration: 1.5,
          ease: "expo.inOut",
        }, '-=1.5')
        .from('.contact__bloc h3', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 1.5,
          ease: "expo.inOut",
        }, '-=1.6')
        .from('.contact__bloc p', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 1.5,
          ease: "expo.inOut",
        }, '-=1.6')
        .from('[data-animate="contact-more-infos"] p ', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 2,
          ease: "expo.inOut",
        }, '-=1.6')


    const tl2 = $gsap.timeline({
      scrollTrigger: {
        trigger: ".contact__appointment",
        start: 'top 80%',
      }
    });

    tl2
        .from('.contact__appointment-title h2', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 1.5,
          ease: "expo.inOut",
        }, '-=0.3')
        .from('.contact__appointment span', {
          opacity: 0,
          y: VERTICAL_TRANSLATION,
          duration: 1.5,
          ease: "expo.inOut",
        }, '-=1.5')
        .from('.contact__appointment .divider', {
          opacity: 1,
          scaleX: 0,
          duration: 1.5,
          ease: "expo.inOut",
        }, '-=1.5')
        .fromTo('.contact__appointment button:nth-child(1)', {y: VERTICAL_TRANSLATION, opacity: 0}, {
          y: 0,
          opacity: 1,
          duration: 2,
          ease: "expo.inOut"
        }, "-=1.8")
        .fromTo('.contact__appointment button:nth-child(2)', {y: VERTICAL_TRANSLATION, opacity: 0}, {
          y: 0,
          opacity: 1,
          duration: 2,
          ease: "expo.inOut"
        }, "-=1.9")
  });
})
</script>