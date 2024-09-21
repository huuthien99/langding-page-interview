<template>
  <div class="footer-info-container">
    <div>
      <div class="image-logo">
        <img alt="logo" class="logo" src="@/assets/logo-footer.png" />
      </div>
      <div class="social">
        <img src="@/assets/icon/twitter.svg" alt="twitter" />
        <img src="@/assets/icon/facebook.svg" alt="facebook" />
        <img src="@/assets/icon/linkedin.svg" alt="linkedin" />
      </div>
    </div>
    <div class="address-subscribe">
      <div class="address">
        <h6 class="title">Address</h6>
        <div class="address-info">
          <img src="@/assets/icon/location.svg" alt="" width="40" height="40" />
          <div class="address-description">
            <p>
              Valletta Buildings, South Street, Valletta - VLT 1103 Malta, US
            </p>
            <p>
              20 Phan Dang Luu street, Hai Chau District, Danang city, Vietnam
            </p>
          </div>
        </div>
        <div class="address-info phone">
          <img src="@/assets/icon/phone.svg" alt="" width="40" height="40" />
          <p>(+1) 555-0108-000 or (+236) 555-0108</p>
        </div>
      </div>
      <div class="subscribe">
        <h6 class="title">Subscribe</h6>
        <p class="title-subscribe">
          Subscribe to our newsletter and be the first to know about our updates
        </p>
        <div class="input">
          <Input>
            <div
              style="
                cursor: pointer;
                display: flex;
                align-items: center;
                height: 100%;
              "
            >
              <ArrowRight></ArrowRight>
            </div>
          </Input>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Input from "../common/Input.vue";
import ArrowRight from "../../assets/icon/ArrowRight.vue";
</script>

<style lang="css" scoped>
/* GLOBAL */
.social {
  display: flex;
  gap: 24px;
}
.title {
  font-family: "Montserrat";
  font-weight: 700;
  font-size: 24px;
  line-height: 30px;
  color: #ffffff;
}
p {
  color: #ffffff;
  font-style: italic;
  font-weight: 400;
  font-family: "Montserrat";
  line-height: 20px;
  font-size: 14px;
}

.address-info {
  display: flex;
  gap: 8px;
}

.address-description {
  display: flex;
  flex-direction: column;
  gap: 12px;
  padding-bottom: 40px;
}

.phone {
  align-items: center;
}

.title-subscribe {
  padding-bottom: 12px;
}

/* end */

@media (min-width: 1366px) {
  .footer-info-container {
    background: url("@/assets/BGFT.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    padding: 104px 230px 100px;
    display: flex;
    gap: 350px;
  }

  .image-logo {
    padding-bottom: 40px;
  }

  .address-subscribe {
    width: 100px;
    display: flex;
    gap: 40px;
    flex: 1;
  }

  .address,
  .subscribe {
    width: 410px;
  }

  .title {
    padding-bottom: 20px;
  }
}

@media (min-width: 375px) and (max-width: 1365px) {
  .footer-info-container {
    display: flex;
    flex-direction: column;
    background: url("@/assets/BGFTMB.png");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    align-items: center;
    padding: 40px 16px 0;
  }
  .image-logo {
    padding-bottom: 40px;
  }

  .social {
    padding-bottom: 68px;
  }
  .title {
    padding-bottom: 20px;
  }
  .address-description {
    padding-bottom: 20px;
  }
  .phone {
    padding-bottom: 68px;
  }

  .title-subscribe {
    padding-bottom: 17px;
  }

  .input {
    padding-bottom: 62px;
  }
}
</style>
