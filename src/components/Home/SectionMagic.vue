<template>
  <section class="magic-section" id="ingredients">
    <div class="magic-section__title-container">
      <h3 class="title--big">
        MAGIQUE !
        <h4 class="title--medium">INCROYABLE MAIS VRAI !</h4>
      </h3>
    </div>
    <div class="slides-container">
      <img src="../../assets/icn_chevron.svg" alt="gauche" class="icn-chevron icn-chevron--left" @click="previous()">
      <img src="../../assets/icn_chevron.svg" alt="droite" class="icn-chevron icn-chevron--right" @click="next()">
      <div class="magic-section__slides-container">
        <div class="slide-content-wrapper" v-for="(slide, index) in magicSlides" :key="index">
          <transition :name="transitionName" mode="out-in">
            <div class="slide-content" v-show="selectedSlideIndex === index" :key="`slide${index}`">
              <div class="slide__image-container">
                <span class="slide-number">{{ slide.number }}.</span>
                <img :src="slide.image" alt="malt" class="slide__img">
              </div>
              <div class="slide__text-container">
                <h3 class="punchline" v-html="slide.title"></h3>
                <p class="slide__description" v-html="slide.content"></p>
              </div>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import magicSlides from '../../const/magicSlides'
const SLIDE_TO_RIGHT = 'slide-to-right'
const SLIDE_TO_LEFT = 'slide-to-left'

export default {
  data: () => ({
    magicSlides,
    selectedSlide: magicSlides[0],
    selectedSlideIndex: 0,
    transitionName: '',
    test: process.env.BASE_URL
  }),
  methods: {
    previous () {
      this.transitionName = SLIDE_TO_RIGHT
      this.selectedSlideIndex = this.selectedSlideIndex === 0
        ? magicSlides.length - 1
        : this.selectedSlideIndex - 1
    },
    next () {
      this.transitionName = SLIDE_TO_LEFT
      this.selectedSlideIndex = this.selectedSlideIndex === magicSlides.length - 1
        ? 0
        : this.selectedSlideIndex + 1
    }
  }
}
</script>

<style lang="scss" scoped>
.magic-section__title-container {
  display: flex;
  justify-content: flex-end;
  padding-right: 7vw;
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
    left: 3px;
    font-size: 50px;
    color: #000;
  }
}
.slides-container {
  position: relative;
  .icn-chevron {
    height: 100px;
    object-fit: contain;
    position: absolute;
    top: 50%;
    cursor: pointer;
    transition: all 0.5s ease;
    z-index: 5;
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
  .slide-number {
    position: absolute;
    top: 20px;
    left: 30px;
    color: #fff;
    font-size: 100px;
    font-family: 'Impact';
  }
  .slide__text-container {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    .punchline {
      margin: 0;
      text-align: left;
      font-size: 50px;
    }
    .slide__description {
      text-align: left;
      font-size: 24px;
      font-style: italic;
      text-align: justify;
    }
  }
  .slide__img {
    margin-right: 40px;
  }
}
.magic-section__slides-container {
  margin: 10px 10vw 0 10vw;
  min-height: 85vh;
  position: relative;
  .slide-content-wrapper {
    position: absolute;
    top: 0;
    left: 0;
    .slide-content {
      display: flex;
      align-items: center;
    }
  }
}

.slide-to-left-enter-active, .slide-to-left-leave-active,
.slide-to-right-enter-active, .slide-to-right-leave-active {
  transition: all 1.2s ease;
}

.slide-to-left-enter {
  transform: translateX(180%);
  opacity: 0.3;
}
.slide-to-left-leave-to {
  transform: translateX(-180%);
  opacity: 0.3;
}

.slide-to-right-enter {
  transform: translateX(-180%);
  opacity: 0;
}
.slide-to-right-leave-to {
  transform: translateX(180%);
  opacity: 0;
}

@media (max-width: 500px) {
  .title--big {
    margin: 10px 0 !important;
    font-size: 38px !important;
  }
  .title--medium {
    font-size: 13px !important;
    bottom: 5px !important;
    left: 2px !important;
    white-space: nowrap;
  }
  .magic-section__slides-container {
    margin: 0;
    min-height: 62vh;
    .slide-content {
      flex-wrap: wrap;
      .slide__image-container {
        margin: 0;
        width: 100%;
        .slide__img {
          max-height: 250px;
          margin: 0;
          width: 100%;
          object-fit: cover;
        }
        .slide-number {
          top: calc(60% + 8px);
          left: 20px;
          font-size: 50px;
          color: #000;
        }
      }
    }
  }
  .slides-container {
    .icn-chevron {
      top: 28%;
      z-index: 5;
      height: 45px;
    }
    .slide__text-container {
      padding: 0 20px 0 70px;
      .punchline {
        margin: 20px 0 !important;
        font-size: 24px !important;
      }
      .slide__description {
        font-size: 12px !important;
        margin-bottom: 20px;
      }
    }
  }
}
</style>
