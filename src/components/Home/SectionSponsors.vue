<template>
  <div class="section-sponsors-container">
    <div class="sponsors__row sponsors__description1">
      <p class="supporters">Ils nous soutiennent</p>
    </div>
    <div class="sponsors__row sponsors__row-1">
      <img src="../../assets/logo_smartfood.png" alt="smartfood" class="so-malte-sponsor smartfood">
      <img src="../../assets/logo_bpi.svg" alt="bpi" class="so-malte-sponsor bpi-france">
    </div>

    <div class="sponsors__row sponsors__description2">
      <p class="supporters">Ils nous font confiance</p>
    </div>
    <div class="sponsors__row sponsors__row-2">
      <img src="../../assets/logo_casaveg.png" alt="Casaveg'" class="so-malte-sponsor casaveg">
      <img src="../../assets/logo_mamayoka.png" alt="mamayoka" class="so-malte-sponsor mamayoka">
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.sponsors__row {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background-color: #e3b190;
  padding: 30px 0;
  .supporters {
    color: #fff;
    font-size: 25px;
    margin: 0;
  }
  .so-malte-sponsor {
    object-fit: contain;
    z-index: 1;
    &.bpi-france {
      height: 6vh;
    }
    &.alphonse-madeleine, &.mamayoka, &.casaveg, &.smartfood {
      height: 9vh;
    }
  }
}
.sponsors__row.sponsors__row-1 {
  padding: 30px 50px;
}
.sponsors__description1 {
  padding-bottom: 0;
}

@media (max-width: 500px) {
  .sponsors__row {
    padding: 20px 0;
    .so-malte-sponsor {
      height: 20px !important;
    }
  }
  .sponsors__description1 {
    padding: 20px 0 0 0;
    p {
      font-size: 15px !important;
    }
  }
  .sponsors__description2 {
    padding: 20px 0 20px 0;
    p {
      font-size: 15px !important;
    }
  }
}
</style>
