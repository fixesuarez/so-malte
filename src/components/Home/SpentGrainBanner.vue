<template>
  <div class="spent-grain-banner-container">
    <div class="banner__text-container">
      <h3 class="banner__punchline">
        LA DRÊCHE DE BRASSERIE,<br />L’OR DE DEMAIN
      </h3>
      <input type="button" value="Découvrez !" class="contact-btn">
    </div>
    <img src="../../assets/magic_1.png" alt="malt" class="banner__background">
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.spent-grain-banner-container {
  position: relative;
  width: 100%;
  height: 30vh;
  margin-top: 120px;
  .banner__background {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    object-fit: cover;
  }
  .banner__text-container {
    padding: 0 200px 0 75px;
    height: 100%;
    position: relative;
    display: flex;
    align-items: center;
    color: #fff;
    z-index: 1;
    justify-content: space-between;
    .banner__punchline {
      margin: 0;
      font-size: 60px;
    }
    .contact-btn {
      font-size: 40px;
      font-weight: bold;
      padding: 10px 20px;
      background-color: transparent;
      color: #fff;
      border-radius: 15px;
      border: 2px solid #fff;
      cursor: pointer;
      &:focus {
        outline:0;
      }
    }
  }
}
</style>