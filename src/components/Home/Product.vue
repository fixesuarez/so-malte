<template>
  <div class="product-root">
    <section class="healthy-tasty-container" id="produits">
      <div class="mask" />
      <img src="../../assets/healthy_tasty.png" alt="sain-gourmand" class="argument-img">
      <div class="text-container">
        <h2 class="punchline">Sain et gourmand, la<br />vaisselle comestible</h2>
        <p class="description">
          Une alternative surprenante à la vaisselle jetable, fabriquée à partir de résidu de malt de bière. Elle
          réduit vos déchets et offre une expérience nouvelle à vos clients.
        </p>
      </div>
    </section>
    <div class="slides-container">
      <img src="../../assets/icn_chevron_white.svg" alt="gauche" class="icn-chevron icn-chevron--left" @click="previous()">
      <img src="../../assets/icn_chevron_white.svg" alt="droite" class="icn-chevron icn-chevron--right" @click="next()">
      <div class="magic-section__slides-container">
        <div class="slide-content-wrapper">
          <transition-group :name="transitionName" mode="out-in">
            <section class="ecology-container" style="background-color: #0d6496" v-show="selectedSlideIndex === 0" key="slidea">
              <div class="text-container">
                <h2 class="product-section-title">SAIN</h2>
                <div class="product-description">
                  <span>En plus d’être délicieux nos produits sont<br/>bon pour la santé :</span>
                  <ul class="ecology-list">
                    <li class="ecology-list__item">Riche en fibres végétales</li>
                    <li class="ecology-list__item">Source de protéines vétégales</li>
                    <li class="ecology-list__item">Faible en glucides</li>
                  </ul>
                  <span class="spaced">De quoi raviver vos papilles et le body !</span>
                </div>
              </div>
              <img src="../../assets/sain.jpg" alt="écologie" class="ecology-icn">
            </section>

            <section class="ecology-container" style="background-color: #d46700" v-show="selectedSlideIndex === 1" key="slidez">
              <div class="text-container">
                <h2 class="product-section-title">GOURMAND</h2>
                <div class="product-description">
                  <span>Ce produit a été <strong>créé avec et pour les consommateur !</strong><br/>
                  Le goût légèrement toasté de Somalté se marie parfaitement avec tous types de plat et de dessert.</span>
                </div>
              </div>
              <img src="../../assets/gourmand.jpg" alt="écologie" class="ecology-icn">
            </section>

            <section class="ecology-container" style="background-color: #275a10" v-show="selectedSlideIndex === 2" key="slidee">
              <div class="text-container">
                <h2 class="product-section-title">ECOLO !</h2>
                <div class="product-description">
                  <span>
                    Nos produits sont de vrais alternatives à la vaisselle jetable !<br/>
                    Une solution 2 en 1 : ça remplace le pain de nos repas et fait office de récipient et à la fin plus de déchets puisque vous l’avez mangé
                  </span>
                </div>
              </div>
              <img src="../../assets/ecologique.jpg" alt="écologie" class="ecology-icn">
            </section>
          </transition-group>
        </div>
      </div>
    </div>
    
    
  </div>
</template>

<script>
const SLIDE_TO_RIGHT = 'slide-to-right'
const SLIDE_TO_LEFT = 'slide-to-left'

export default {
  data: () => ({
    selectedSlideIndex: 0,
    transitionName: ''
  }),
  methods: {
    previous () {
      this.transitionName = SLIDE_TO_RIGHT
      this.selectedSlideIndex = this.selectedSlideIndex === 0
        ? 2
        : this.selectedSlideIndex - 1
    },
    next () {
      this.transitionName = SLIDE_TO_LEFT
      this.selectedSlideIndex = this.selectedSlideIndex === 2
        ? 0
        : this.selectedSlideIndex + 1
    }
  }
}
</script>

<style lang="scss" scoped>
// #produits {
//   opacity: 0;
// }
// #produits.visible {
//   opacity: 1;
// }
.healthy-tasty-container {
  position: relative;
  padding: 100px;
  width: 100vw;
  max-width: 100vw;
  transform: translateY(-4px);
  box-sizing: border-box;
  display: flex;
  .mask {
    position: absolute;
    top: 1px;
    left: 0;
    height: 100%;
    width: calc(20% + 50px);
    background-color: #ffdf80;
  }
  .argument-img {
    z-index: 1;
    max-width: 40%;
    object-fit: cover;
  }
  .text-container {
    padding: 0 50px 0 100px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    .punchline {
      text-align: left;
      font-weight: bold;
      font-size: 50px;
    }
    .description {
      text-align: left;
      font-size: 26px;
      font-style: italic;
    }
    .quote {
      margin: 40px 0;
      font-size: 20px;
      font-weight: bold;
      text-align: right;
      .quote-citation {
        display: inline-block;
        margin-right: 30px;
      }
      .quote-element {
        font-size: 40px;
        line-height: 25px;
      }
    }
  }
}

.slides-container {
  position: relative;
  .icn-chevron {
    height: 100px;
    object-fit: contain;
    position: absolute;
    top: 52%;
    cursor: pointer;
    z-index: 4;
    transition: all 0.5s ease;
    &.icn-chevron--left {
      transform: translateY(-50%);
      left: 2vw;
      &:hover {
        transform: translateY(-50%) scale(1.2);
      }
    }
    &.icn-chevron--right {
      right: 3vw;
      transform: translateY(-70%) rotate(180deg);
      &:hover {
        transform: translateY(-70%) rotate(180deg) scale(1.2);
      }
    }
  }
}
.magic-section__slides-container {
  min-height: 70vh;
  height: 70vh;
  position: relative;
  .slide-content-wrapper {
    .slide-content {
      height: 100%;
      position: absolute;
      display: flex;
    }
  }
  .slide__image-container {
    position: relative;
    min-width: 45%;
    margin-right: 40px;
    .slide-number {
      position: absolute;
      top: 20px;
      left: 30px;
      color: #fff;
      font-size: 100px;
      font-family: 'Impact';
    }
    .slide__img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
  .slide__text-container {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    .punchline {
      text-align: left;
      font-size: 50px;
      margin: 100px 0 20px 0;
    }
    .slide__description {
      margin: 0 0 100px 0;
      text-align: left;
      font-size: 24px;
      font-style: italic;
    }
  }
}
.slide-to-left-enter-active, .slide-to-left-leave-active,
.slide-to-right-enter-active, .slide-to-right-leave-active {
  transition: all 1.6s ease;
}
.slide-to-left-enter {
  transform: translateX(100%) translateY(-4px) !important;
  // opacity: 0.3;
}
.slide-to-left-leave-to {
  transform: translateX(-100%) translateY(-4px) !important;
  // opacity: 0.3;
}

.slide-to-right-enter {
  transform: translateX(-100%) translateY(-4px) !important;
  opacity: 0;
}
.slide-to-right-leave-to {
  transform: translateX(100%) translateY(-4px) !important;
  opacity: 0;
}

.ecology-container {
  width: 100%;
  display: flex;
  transform: translateY(-4px);
  position: absolute;
  top: 0;
  left: 0;
  .text-container {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 100px 50px 100px 150px;
    * {
      color: #fff;;
    }
    .product-section-title {
      margin-top: 0;
      font-weight: bold;
      font-size: 70px;
    }
    .product-description {
      font-style: italic;
      text-align: left;
      span {
        font-size: 26px;
        text-align: left;
      }
      .ecology-list {
        list-style-type: '-';
        margin: 0;
        padding: 0 0 0 10px;
        .ecology-list__item {
          font-size: 26px;
        }
      }
      .spaced {
        display: inline-block;
        margin-top: 30px;
      }
    }
  }
  .ecology-icn {
    flex: 1;
    max-width: 50%;
    min-width: 50%;
    max-height: 70vh;
    object-fit: cover;
  }
}

@media (max-width: 500px) {
  .healthy-tasty-container {
    flex-wrap: wrap;
    padding: 20px;
    .mask {
      width: 50%;
      height: calc(50vh + 40px);
    }
    .argument-img {
      height: 50vh;
      width: 100%;
      max-width: unset;
    }
    .text-container {
      padding: 0 10px;
      .punchline {
        margin-top: 50px;
        font-size: 34px;
      }
      .description {
        margin-top: 0;
        font-size: 16px;
        text-align: justify;
      }
      .quote {
        margin: 10px 0;
        font-size: 13px;
      }
    }
  }

  .ecology-container {
    flex-wrap: wrap-reverse;
    flex-direction: column-reverse;
    .ecology-icn {
      max-width: 100%;
    }
    .text-container {
      padding: 30px 40px 30px 50px;
      min-height: 300px;
      box-sizing: border-box;
      .product-section-title {
        font-size: 45px;
      }
      .product-description * {
        font-size: 16px !important;
      }
    }
  }
  .quote-element--1 {
    margin-right: 20px;
  }
  .quote-citation {
    display: inline !important;
  }
  .slide-to-left-enter-active, .slide-to-left-leave-active,
  .slide-to-right-enter-active, .slide-to-right-leave-active {
    transition: all 1s ease;
  }
  .slides-container {
    .icn-chevron {
      top: 50%;
      height: 70px;
    }
  }
  .magic-section__slides-container {
    min-height: 75vh;

  }
}

</style>
