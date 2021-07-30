<template>
  <div class="home-root">
    <section class="layout-home">
      <img src="../assets/home_banner.jpg" alt="banner" class="home-banner__img">
      <div class="menu-container">
        <img src="../assets/logo_somalté_blanc.png" alt="logo" class="banner__logo">
        <nav class="menu">
          <ul>
            <li class="menu-item"><a href="#produits">Produits</a></li>
            <li class="menu-item"><a href="#ingredients">Ingrédients magiques</a></li>
            <li class="menu-item"><a href="#a-table">A table !</a></li>
            <li class="menu-item"><a href="#equipe">L'équipe</a></li>
          </ul>
        </nav>
        <h1 class="punchline">CHANGEZ VOTRE VISION DE<br />LA CONSOMMATION</h1>
        <p class="slogan">La vaisselle comestible et gourmande, qui ne laisse<br />aucun déchet derrière elle !</p>
        <a class="contact-btn" href="mailto: hello@somalte.com">Contactez-nous</a>
        <a href="#produits"><img src="../assets/icn_chevron_down_white.svg" class="chevron-down"></a>
      </div>
    </section>
    <Product />
    <SectionWahou />
    <SectionMagic />
    <!-- <SpentGrainBanner /> -->
    <SectionCrazy />
    <SectionTeam />
    <SectionSponsors />
    <Footer />
  </div>
</template>

<script>
import Product from '../components/Home/Product'
import SectionWahou from '../components/Home/SectionWahou'
import SectionMagic from '../components/Home/SectionMagic'
// import SpentGrainBanner from '../components/Home/SpentGrainBanner'
import SectionCrazy from '../components/Home/SectionCrazy'
import SectionTeam from '../components/Home/SectionTeam'
import SectionSponsors from '../components/Home/SectionSponsors'
import Footer from '../components/Home/Footer'

// import ScrollMagic from 'scrollmagic'

export default {
  components: {
    Product,
    SectionWahou,
    SectionMagic,
    // SpentGrainBanner,
    SectionCrazy,
    SectionTeam,
    SectionSponsors,
    Footer
  }
}
</script>

<style lang="scss" scoped>
.layout-home {
  width: 100%;
  max-width: 100vw;
  background-size: 100% auto;
  .home-banner__img {
    object-fit: cover;
    max-height: 100vh;
    height: 100vh;
    max-width: 100%;
    width: 100%;
  }
  .menu-container {
    position: absolute;
    left: 0;
    top: 50px;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    .banner__logo {
      max-width: 15%;
    }
    .menu ul {
      list-style: none;
      margin: 40px 0 0 0;
      padding: 0;
      display: flex;
      .menu-item {
        font-style: italic;
        a {
          position: relative;
          text-decoration: none;
          display: inline-block;
          color: #fff;
          &:after {
            content: '';
            height: 2px;
            width: 0%;
            background-color: #fff;
            position: absolute;
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%);
            transition: width 0.4s ease;
          }
          &:hover::after {
            width: 100%;
          }
        }
        a:visited {
          color: #fff;
        }
        a:-webkit-any-link {
          color: #fff !important;
        }
        color: #fff !important;
        font-size: 25px;
        white-space: nowrap;
        &:not(:first-child) {
          margin-left: 120px;
        }
      }
    }
    .punchline {
      margin: 10vh 0 7vh 0;
      letter-spacing: 3px;
      font-family: "Impact";
      font-size: 70px;
      color: #fff;
    }
    .slogan {
      color: #fff;
      font-size: 30px;
      font-style: italic;
      margin: 0 0 7vh 0;
    }
    .contact-btn {
      font-size: 30px;
      padding: 10px 5px;
      background-color: transparent;
      color: #fff;
      border-radius: 20px;
      border: 2px solid #fff;
      cursor: pointer;
      text-decoration: none;
      &:focus {
        outline:0;
      }
    }
  }
}
.chevron-down {
  position: absolute;
  top: 112%;
  left: 50%;
  height: 40px;
  animation: floating 1s ease infinite alternate-reverse;
  cursor: pointer;
}

@keyframes floating {
  from {
    transform: translate(-50%, 0px);
  }
  to {
    transform: translate(-50%, 20px);
  }
}

@media (max-width: 500px) {
  .banner__logo {
    max-width: unset !important;
    width: 75px;
  }
  .menu-item {
    font-size: 14px !important;
    margin: 0 10px !important;
  }
  .punchline {
    letter-spacing: 2px !important;
    font-size: 35px !important;
    max-width: 75%;
  }
  .slogan {
    font-size: 20px !important;
    max-width: 70%;
  }
  .contact-btn {
    font-weight: bold;
    font-size: 18px !important;
    border-radius: 12px !important;
    border-width: 1px !important;
    padding: 7px 5px !important;
  }
}
</style>