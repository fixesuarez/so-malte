<template>
  <section class="section-team-container" id="equipe">
    <img src="../../assets/team.jpg" alt="team" class="section-team__img">
    <div class="section-team__text-container">
      <h2 class="section__title">L’EQUIPE DE CHOC !</h2>
      <p class="section__description">
        Nous nous sommes rencontrées pendant nos études de Design Industriel où nous avons suivi des cursus différents : produit et interaction.
        Durant un échange en Inde, nous sommes devenues très proches. Nous avons pris conscience de l’urgence écologique.
        Il nous est apparu primordial d’utiliser nos compétences de designer afin d'œuvrer pour la transition écologique.
        <br/><br/>
        Notre projet débute en 2019 autour d’une bière, où nous nous sommes posé la question toute simple : comment fait-on de la <span class="no-wrap">bière ?</span>
        Ce jour-là, nous avons découvert la drêche, son impact et ses bienfaits et nous avons proposé notre produit lors d’un concours…
        L’aventure a commencé !
      </p>
    </div>
  </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.section-team-container {
  padding: 100px 10vw;
  display: flex;
  .section-team__img {
    width: 30%;
    min-width: 30%;
    object-fit: contain;
  }
  .section-team__text-container {
    margin: 0 80px;
    text-align: left;
    .section__title {
      font-size: 60px;
    }
    .section__description {
      font-size: 26px;
      text-align: justify;
    }
  }
}

@media (max-width: 500px) {
  .section-team-container {
    padding: 20px 0;
    .section-team__text-container {
      margin: 0 20px 0 20px;
      .section__title {
        font-size: 16px;
      }
      .section__description {
        font-size: 11px;
      }
    }
  }
}
</style>
