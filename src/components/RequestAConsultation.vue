<script setup>
import {ref} from "vue";

const windowWidth = ref(window.innerWidth >= 768)

window.addEventListener('resize', () => {
  windowWidth.value = window.innerWidth >= 768
})

</script>

<template>
  <div class="request-a-consultation">
    <div class="request-a-consultation_content">
      <h1 class="request-a-consultation_header">Запросить консультацию</h1>
      <p class="request-a-consultation_text">Екатеринбургский центре МНТК «Микрохирургия глаза» предоставляет
        современные
        персонализированные медицинские услуги в области офтальмологии пциентам со всего мира.
        <br>
        <br>
        Наш центр —один из самых крупных работающийх офтальмологический центров в Росcии, являющейся лучшей частной
        организацие в стране. </p>
      <strong class="request-a-consultation_notice">Запросите консультацию, и куратор Департамента международных
        пациентов
        свяжется с вами в&nbsp;ближайшее время:</strong>
      <div class="request-a-consultation_button-wrapper">
        <button class="request-a-consultation_button">Новый пациент</button>
        <button class="request-a-consultation_button">Повторное посещение</button>
        <button class="request-a-consultation_button">Записать пациента</button>
      </div>
    </div>
    <img class="request-a-consultation_img" :src="windowWidth ? '/src/assets/images/Group%20Request%20a%20consultation.png' : '/src/assets/images/Group%20Request%20a%20consultation%202.png'" alt="">
  </div>
</template>

<style scoped>

.request-a-consultation {
  display: flex;
  padding: 32px;
  gap: 30px;
  border-radius: 20px;
  background: var(--Background-1);
}

.request-a-consultation_content {
  max-width: 748px;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.request-a-consultation_header {
  color: var(--Main);
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.64px;
  text-transform: uppercase;
}

.request-a-consultation_text {
  color: var(--Text-2);
  font-size: 16px;
}

.request-a-consultation_notice {
  color: var(--Text-2);
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
}

.request-a-consultation_button-wrapper {
  display: flex;
  align-items: center;
  gap: 12px;
}

.request-a-consultation_button {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 16px 28px;
  border-radius: 12px;
  font-size: 14px;
  font-weight: 700;
  letter-spacing: -0.28px;
  text-transform: uppercase;
  white-space: nowrap;
  margin-top: 36px;
}

.request-a-consultation_button:nth-child(1) {
  background: #F9B532;
  color: var(--White);
  width: 230px;
}

.request-a-consultation_button:nth-child(2) {
  background: var(--White);
  color: #132E6B;
}

.request-a-consultation_button:nth-child(3) {
  color: #132E6B;
}

.request-a-consultation_img {
  max-width: 344px;
  width: 100%;
  max-height: 320px;
}

@media (max-width: 1200px) {

  .request-a-consultation {
    flex-direction: column-reverse
  }
}

@media (max-width: 768px) {

  .request-a-consultation {
    padding: 30px 32px;
  }

  .request-a-consultation_content {
    gap: 20px;
  }

  .request-a-consultation_header {
    font-size: 28px;
    letter-spacing: -0.56px;
  }

  .request-a-consultation_text {
    color: var(--Text-2);
    font-size: 16px;
  }

  .request-a-consultation_notice {
    font-weight: 500;
    line-height: 24px;
  }

  .request-a-consultation_button-wrapper {
    flex-direction: column;
  }

  .request-a-consultation_button {
    margin-top: 0;
  }

  .request-a-consultation_button:nth-child(1) {
    width: 100%;
  }

  .request-a-consultation_button:nth-child(2) {
    width: 100%;
  }

  .request-a-consultation_button:nth-child(3) {
    width: 100%;
  }
}

</style>
