<template>
  <section class="section-wahou">
    <div class="magic-section__title-container">
      <h3 class="title--big">
        WAOUH !
        <h4 class="title--medium">VOUS ALLEZ ADORER !</h4>
      </h3>
    </div>
    <div class="section-content-container">
      <div class="argument-container">
        <span class="argument__label">100% comestible</span>
        <img v-if="isMobile" src="../../assets/03-Wahoo-comestible_mobile.jpg" alt="Comestible" class="argument__img">
        <img v-else src="../../assets/03-Wahoo-comestible.svg" alt="Comestible" class="argument__img">
      </div>
      <div class="argument-container">
        <img v-if="isMobile" src="../../assets/03-Wahoo-Fabriqué-en-france_mobile.jpg" alt="Made in France" class="argument__img">
        <img v-else src="../../assets/03-Wahoo-Fabriqué-en-france.svg" alt="Made in France" class="argument__img">
        <span class="argument__label">Fabriqué en France</span>
      </div>
      <div class="argument-container">
        <span class="argument__label" style="margin-bottom: 20px">Expérience culinaire</span>
        <img v-if="isMobile" src="../../assets/03-Wahoo-expérience-culinaire_mobile.jpg" alt="Expérience culinaire" class="argument__img">
        <img v-else src="../../assets/03-Wahoo-expérience-culinaire_mobile.png" alt="Expérience culinaire" class="argument__img">
      </div>
    </div>
  </section>
</template>

<script>
export default {
  computed: {
    isMobile () {
      return window.innerWidth <= 500
    }
  }
}
</script>

<style lang="scss" scoped>
.magic-section__title-container {
  display: flex;
  padding-left: 7vw;
  margin-bottom: 40px;
  .title--big {
    margin: 20px 0;
    display: inline-block;
    position: relative;
    font-size: 140px;
    color: #aaa;
    letter-spacing: 3px;
  }
  .title--medium {
    margin: 0;
    position: absolute;
    bottom: 20px;
    left: 8px;
    font-size: 50px;
    color: #000;
  }
}
.section-content-container {
  display: flex;
  padding: 0 5vw;
  margin-bottom: 50px;
  .argument-container {
    display: flex;
    flex-direction: column;
    flex: 1;
    &:not(:first-child) {
      margin-left: 40px;
    }
    .argument__img {
      width: 100%;
    }
    .argument__label {
      font-weight: bold;
      font-size: 20px;
    }
  }
}

@media (max-width: 500px) {
  .title--big {
    margin: 10px 0 !important;
    font-size: 65px !important;
  }
  .title--medium {
    font-size: 22px !important;
    bottom: 10px !important;
    left: 5px !important;
  }
  .section-content-container {
    flex-wrap: wrap;
    .argument-container {
      margin: 10px 0 !important;
      width: 100%;
      flex: unset;
      .argument__label {
        display: none;
      }
    }
  }
}
</style>
