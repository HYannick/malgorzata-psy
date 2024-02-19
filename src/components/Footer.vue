<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__divider"></div>
      <div class="footer__content">
        <p class="text-paragraph-3">2024 © Małgorzata Orzechowska</p>
        <p class="text-paragraph-3">Design :: <span class="-text-bold">Jakub Górzny</span> / Dev :: <span class="-text-bold">ayho</span> </p>
      </div>
    </div>
  </footer>
</template>
<style>
.footer__divider {
  width: 100%;
  height: 0.1rem;
  background-color: var(--color-primary);
  margin: 0 auto;
}

.footer {
  color: var(--color-primary);
}

.footer__content {
  display: flex;
  justify-content: space-between;
  padding: 1.6rem;
  @media screen and (max-width: 768px) {
    flex-direction: column;
    gap: 1.6rem;
  }
}
</style>