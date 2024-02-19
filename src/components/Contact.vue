<template>
  <section id="contact" class="contact">
    <div class="contact__infos">
      <div class="container">
        <div class="contact__heading">
          <h2 class="text-display">Kontakt</h2>
        </div>
        <div class="contact__blocs">
          <div class="contact__bloc">
            <h3 class="text-paragraph-large -text-bold">GABINETY</h3>
            <p class="text-paragraph-2">Radzyń ul. Ostrowiecka 38<br>(Wejście z tyłu budynku od parkingu)</p>
            <br>
            <p class="text-paragraph-2">Łuków ul. Rogalińskiego 8</p>
          </div>
          <div class="horizontal-divider"></div>
          <div class="contact__bloc">
            <h3 class="text-paragraph-large -text-bold">Telefon</h3>
            <p class="text-paragraph-2">Zadzwoń, porozmawiajmy</p>
            <br>
            <p class="text-paragraph-2">+48 660 667 093</p>
          </div>
          <div class="horizontal-divider"></div>
          <div class="contact__bloc">
            <h3 class="text-paragraph-large -text-bold">E-mail</h3>
            <p class="text-paragraph-2">Napisz, pomogę</p>
            <br>
            <p class="text-paragraph-2">orzechowska.terapeuta@gmail.com</p>
          </div>
        </div>
        <p class="text-paragraph-1">W wyjątkowych przypadkach istnieje również możliwość sesji online</p>
      </div>
    </div>
    <div class="contact__appointment">
      <div class="container">
        <h2 class="about__title text-display">Zapraszam na spotkanie</h2>
        <span class="text-paragraph-3 -text-light">MAŁGORZATA ORZECHOWSKA</span>
        <div class="divider"></div>
        <div class="contact__appointment-actions">
          <button class="button button__primary -text-light">ZNAJDŹ GABINET</button>
          <button class="button button__outline -text-light">WYŚLIJ MAIL’A</button>
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


.contact__heading h2 {
  line-height: 1.3;
  margin-bottom: 12.8rem;
}

.contact__heading span {
  display: block;
  margin-bottom: 3.6rem;
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
.contact__blocs h3 {
  letter-spacing: 0.5rem;
  text-transform: uppercase;
  margin-bottom: 3.2rem;
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
  @media screen and (max-width: 768px) {
    flex-direction: column;
  }
}
</style>
<script setup lang="ts">
</script>