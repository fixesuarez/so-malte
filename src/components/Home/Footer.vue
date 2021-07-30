<template>
  <div class="footer-container">
    <img src="../../assets/Somalté-GIF.gif" alt="gif-footer" class="footer__gif">
    <div class="contact-container">
      <span class="contact-title">Contactez-nous !</span>
      <div class="contact-item-container">  
        <img src="../../assets/picto_mail.svg" alt="email" class="contact__icn">
        <span class="contact__value">hello[a]somalte.com</span>
      </div>
      <div class="follow-container">
        <span class="contact-title">Suivez-nous !</span>
        <div class="icons-container">
          <a class="social-network" href="https://www.instagram.com/somalte.s/?hl=fr" target="_blank">
            <img src="../../assets/picto_instagram.svg" alt="Instagram" >
          </a>
          <a href="https://www.facebook.com/SoMalte.es" target="_blank" class="social-network">
            <img src="../../assets/picto_facebook.svg" alt="Facebook">
          </a>
          <a href="https://www.linkedin.com/company/somalt%C3%A9/" target="_blank" class="social-network">
            <img src="../../assets/picto_linkedin.svg" alt="LinkedIn">
          </a>
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
.footer-container {
  padding: 30px 0;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background-color: #e3b190;
  .footer__gif {
    height: 280px;
    object-fit: contain;
  }
  .contact-container {
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    color: #fff;
    .contact-title {
      margin-bottom: 20px;
      font-size: 22px;
      font-weight: bold;
    }
    .contact-item-container {
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      .contact__icn {
        width: 50px;
        margin-right: 20px;
      }
      .contact__value {
        font-weight: bold;
        font-size: 18px;
      }
    }
    .follow-container {
      margin-top: 40px;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      .icons-container {
        display: flex;
        .social-network {
          width: 50px;
          &:not(:last-child) {
            margin-right: 20px;
          }
        }
      }
    }
  }
}

@media (max-width: 500px) {
  .footer-container {
    padding: 20px 0;
    .footer__gif {
      height: 150px;
    }
    .contact-container {
      .contact-title {
        font-size: 14px;
        margin-bottom: 10px;
      }
      .contact-item-container {
        margin-bottom: 10px;
        .contact__icn {
          width: 25px;
        }
        .contact__value {
          font-size: 10px;
        }
      }
    }
    .follow-container {
      margin-top: 10px !important;
      .social-network {
        width: 35px !important;
        margin-right: 10px !important;
      }
    }
  }
}
</style>
