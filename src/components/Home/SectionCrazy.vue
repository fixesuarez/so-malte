<template>
  <div class="section-crazy-container" id="a-table">
    <div class="section-crazy__title-container">
      <h3 class="title--big">
        C'EST FOU !
        <h4 class="title--medium">CE QU'ON VOUS PROPOSE...</h4>
      </h3>
    </div>
    <div class="gallery-container">
      <div class="column">
        <div class="gallery-img-container">
          <img src="../../assets/crazy1.jpg" alt="plat vert" class="gallery__img">
          <div class="mask">
            <span>Traiteur</span>
          </div>
        </div>
      </div>
      <div class="column column-2">
        <div class="gallery-img-container">
          <img src="../../assets/ecology.jpg" alt="" class="gallery__img">
          <div class="mask">
            <span>Apéritif</span>
          </div>
        </div>
        <div class="gallery-img-container">
          <img src="../../assets/crazy2.jpg" alt="plat vert" class="gallery__img">
          <div class="mask">
            <span>Buffet</span>
          </div>
        </div>
      </div>
      <div class="column column-3">
        <div class="gallery-img-container">
          <img src="../../assets/crazy3.jpg" alt="" class="gallery__img">
          <div class="mask">
            <span>Cocktail</span>
          </div>
        </div>
        <div class="gallery-img-container">
          <img src="../../assets/crazy4.jpg" alt="plat vert" class="gallery__img">
          <div class="mask">
            <span>Drèch'jeuner</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.section-crazy-container {
  margin-top: 100px;
}
.section-crazy__title-container {
  // margin-top: 80px;
  display: flex;
  padding-left: 5vw;
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
.gallery-container {
  max-height: 70vh;
  padding: 35px 6vw;
  display: flex;
  justify-content: space-between;
  .gallery-img-container {
    position: relative;
    .mask {
      position: absolute;
      height: 100%;
      width: 100%;
      top: 0;
      left: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      span {
        opacity: 0;
        font-size: 40px;
      }
      &:hover {
        transition: background-color 0.3s ease;
        background-color: rgba(255, 255, 255, 0.7);
        span {
          opacity: 1;
        }
      }
    }
  }
  .column:first-child {
    width: 45%;
    .gallery-img-container {
      height: 100%;
      img {
        height: 100%;
        width: 100%;
        object-fit: cover;
      }
    }
  }
  .column:not(:first-child) {
    width: 25%;
  }
  .column-2 {
    padding: 0px 0;
    display: flex;
    flex-direction: column;
    .gallery-img-container:first-child {
      height: calc(65% - 20px);
      margin-bottom: 2vw;
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .gallery-img-container:not(:first-child) {
      height: calc(45% - 20px);
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }

  .column-3 {
    padding: 0px 0;
    display: flex;
    flex-direction: column;
    .gallery-img-container:first-child {
      height: calc(45% - 20px);
      margin-bottom: 2vw;
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .gallery-img-container:not(:first-child) {
      height: calc(65% - 20px);
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}

@media (max-width: 500px) {
  .section-crazy-container {
    margin: 25px 0 50px 0;
    .section-crazy__title-container {
      margin-top: 0;
      .title--big {
        font-size: 40px;
        margin-bottom: 0;
      }
      .title--medium {
        font-size: 14px;
        white-space: nowrap;
        bottom: 5px;
        left: 2px;

      }
    }
    .gallery-container {
      max-height: 40vh;
      padding: 20px 0 0 0;
    }
  }
}
</style>
