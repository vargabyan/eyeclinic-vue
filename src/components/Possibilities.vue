<script setup>

</script>

<template>
  <div class="possibilities container-offset">
    <h1 class="possibilities_header">Возможности</h1>
    <div class="possibilities_content">
      <div class="possibilities_description">
        <div class="possibilities_teg-wrapper">
          <button class="possibilities_tag-item possibilities_tag-item-active">Оснащение</button>
          <button class="possibilities_tag-item">Скорость</button>
          <button class="possibilities_tag-item">Эффективность</button>
        </div>
        <div class="possibilities_counter-wrapper">
          <p class="possibilities_counter">1/<span>3</span></p>
        </div>
        <div class="possibilities_tex-wrapper">
          <h2 class="possibilities_test-header">Современное оснащение</h2>
          <p class="possibilities_text">
            Клиника располагает мощной диагностической линией, оснащенными ультрасовременными технологиями операционными
            залами, прекрасным стационаром.В настоящее время в Екатеринбурге работают: два отделения охраны детского
            зрения, Центр рефракционно-лазерной хирургии, городское отделение диагностики и лечения глаукомы, оптический
            салон.
          </p>
        </div>
      </div>
      <img class="possibilities_img" src="/src/assets/images/image%2034.png" alt="">
    </div>
  </div>
</template>

<style scoped>

.possibilities {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.possibilities_header {
  color: var(--Main);
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.64px;
}

.possibilities_content {
  display: flex;
  justify-content: space-between;
  gap: 50px;
}

.possibilities_description {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.possibilities_teg-wrapper {
  display: flex;
  gap: 12px;
}

.possibilities_tag-item {
  display: flex;
  padding: 12px 14px;
  gap: 10px;
  border-radius: 6px;
  background: var(--Tretiary);
  color: var(--Black);
  font-size: 14px;
  letter-spacing: -0.28px;
}

.possibilities_tag-item-active {
  background: var(--Background-1);
}

.possibilities_counter-wrapper {
  display: flex;
  padding: 8px 10px;
  justify-content: flex-end;
  align-items: center;
  gap: 10px;
  border-bottom: 1px solid var(--Background-1);
}

.possibilities_counter {
  color: var(--Text);
  font-size: 16px;
  letter-spacing: -0.32px;
}

.possibilities_counter span {
  color: #000;
}

.possibilities_tex-wrapper {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.possibilities_test-header {
  color: var(--Main);
  font-size: 24px;
  font-weight: 700;
  line-height: 32px;
  text-transform: uppercase;
}

.possibilities_text {
  color: var(--Text-2);
  font-size: 16px;
}

.possibilities_img {
  max-width: 502px;
  width: 100%;
  max-height: 387px;
  border-radius: 13px;
  background-repeat: no-repeat;
  background-size: cover;
}

</style>