<script setup>
import FaqItem from '/src/components/faq/FaqItem.vue'
import {ref} from 'vue'

const responseData = [
  {
    question: 'Вы помогаете с трансфером из аэропорта?',
    answer: 'Да, в нашей клинике можно приобрести солнцезащитные очки с диоптриями под заказ. Для этого Вам нужно записаться на прием к врачу для выписки рецепта на очки. Приём у врача проходит по предварительной записи. Или если у Вас есть рецепт, то просто подойти в наш салон для заказа.\n' +
        'Срок ожидания заказа до 1 месяца.\n' +
        'Салон  оптики при нашей клиники работает без выходных с 09:00 до 20:00, прием у врача начинается с 10 часов.\n',
  },
  {
    question: 'Могу ли я записать своего родственника, друга?',
    answer: 'Да, в нашей клинике можно приобрести солнцезащитные очки с диоптриями под заказ. Для этого Вам нужно записаться на прием к врачу для выписки рецепта на очки. Приём у врача проходит по предварительной записи. Или если у Вас есть рецепт, то просто подойти в наш салон для заказа.\n' +
        'Срок ожидания заказа до 1 месяца.\n' +
        'Салон  оптики при нашей клиники работает без выходных с 09:00 до 20:00, прием у врача начинается с 10 часов.\n',
  },
  {
    question: 'В какой валюте происходит оплата услуг?',
    answer: 'Да, в нашей клинике можно приобрести солнцезащитные очки с диоптриями под заказ. Для этого Вам нужно записаться на прием к врачу для выписки рецепта на очки. Приём у врача проходит по предварительной записи. Или если у Вас есть рецепт, то просто подойти в наш салон для заказа.\n' +
        'Срок ожидания заказа до 1 месяца.\n' +
        'Салон  оптики при нашей клиники работает без выходных с 09:00 до 20:00, прием у врача начинается с 10 часов.\n',
  },
  {
    question: 'Действуют ли в клинике скидки ветеранам труда, труженникам тыла?',
    answer: 'Да, в нашей клинике можно приобрести солнцезащитные очки с диоптриями под заказ. Для этого Вам нужно записаться на прием к врачу для выписки рецепта на очки. Приём у врача проходит по предварительной записи. Или если у Вас есть рецепт, то просто подойти в наш салон для заказа.\n' +
        'Срок ожидания заказа до 1 месяца.\n' +
        'Салон  оптики при нашей клиники работает без выходных с 09:00 до 20:00, прием у врача начинается с 10 часов.\n',
  },
  {
    question: 'У моей матери на одном глазу поставили диагноз катаракта,на другом глоукома.Сколько будут стоить операции с данными проблемами.Ветеран труда.Существуют ли какие-то льготы?',
    answer: 'Да, в нашей клинике можно приобрести солнцезащитные очки с диоптриями под заказ. Для этого Вам нужно записаться на прием к врачу для выписки рецепта на очки. Приём у врача проходит по предварительной записи. Или если у Вас есть рецепт, то просто подойти в наш салон для заказа.\n' +
        'Срок ожидания заказа до 1 месяца.\n' +
        'Салон  оптики при нашей клиники работает без выходных с 09:00 до 20:00, прием у врача начинается с 10 часов.\n',
  },
  {
    question: 'Есть ли эффективные народные методы лечения варикоцеле?',
    answer: 'Да, в нашей клинике можно приобрести солнцезащитные очки с диоптриями под заказ. Для этого Вам нужно записаться на прием к врачу для выписки рецепта на очки. Приём у врача проходит по предварительной записи. Или если у Вас есть рецепт, то просто подойти в наш салон для заказа.\n' +
        'Срок ожидания заказа до 1 месяца.\n' +
        'Салон  оптики при нашей клиники работает без выходных с 09:00 до 20:00, прием у врача начинается с 10 часов.\n',
  },
]

const windowWidth = ref(window.innerWidth <= 768)
const items = ref(responseData)
const handle = ref(false)

const action = (param) => {
  if (param.value) {
    items.value = responseData.filter((value, index) => {

      if (index < 2) {
        return value
      }
    })
  } else {
    items.value = responseData
  }
}

window.addEventListener('resize', () => {
  windowWidth.value = window.innerWidth <= 768
  action(windowWidth)
})

const handleOpen = () => {
  handle.value = !handle.value
  action(handle)
}

</script>

<template>
  <div class="faq container-offset">
    <div class="faq_header-wrapper">
      <h1 class="faq_header">Часто задаваемые вопросы</h1>
      <a class="faq_view-all" href="" v-show="windowWidth">Посмотреть все</a>
    </div>
    <div class="faq_content">
      <div class="faq_content_item" v-for="item in items">
        <FaqItem v-bind:item="item"/>
      </div>
    </div>

    <strong class="faq_footer-button" v-show="windowWidth">
      Смотреть все популярные вопросы
      <span @click="handleOpen">ещё 4  вопроса</span>
    </strong>
  </div>
</template>

<style scoped>

.faq {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.faq_header {
  color: var(--Text-Heading);
  font-size: 40px;
  font-weight: 700;
  letter-spacing: -0.8px;
  display: flex;
  justify-content: space-between;
}

.faq_content {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.faq_content_item {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

@media (max-width: 768px) {

  .faq {
    gap: 15px;
    padding: 0 !important;
  }

  .faq_header-wrapper {
    display: flex;
    justify-content: space-between;
    padding: 40px 32px 0 32px;
  }

  .faq_header {
    max-width: 155px;
    font-size: 26px;
    letter-spacing: -0.52px;
  }

  .faq_view-all {
    color: var(--Main);
    font-size: 14px;
    font-weight: 500;
    letter-spacing: -0.28px;
    padding: 8px 14px;
    border-radius: 8px;
    background: rgba(229, 236, 240, 0.50);
    height: min-content;
  }

  .faq_footer-button {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 12px;
    padding: 0 32px 40px 32px;
    margin-top: 12px;
  }

  .faq_footer-button {
    color: var(--Black);
    font-size: 16px;
    font-weight: 500;
  }

  .faq_footer-button span {
    color: var(--Text);
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .faq_footer-button span:after {
    display: block;
    content: '';
    width: 14px;
    height: 10px;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='15' height='11' viewBox='0 0 15 11' fill='none'%3E%3Cpath d='M7.53906 10.9766C7.67448 10.9766 7.79948 10.9505 7.91406 10.8984C8.02865 10.8463 8.13802 10.7682 8.24219 10.6641L14.1953 4.57812C14.3672 4.40625 14.4531 4.19271 14.4531 3.9375C14.4531 3.77083 14.4115 3.61719 14.3281 3.47656C14.25 3.33594 14.1432 3.22396 14.0078 3.14062C13.8724 3.0625 13.7187 3.02344 13.5469 3.02344C13.3021 3.02344 13.0833 3.11719 12.8906 3.30469L7.53906 8.78906L2.18754 3.30469C1.99484 3.11719 1.77344 3.02344 1.52344 3.02344C1.35674 3.02344 1.20574 3.0625 1.07034 3.14062C0.929636 3.22396 0.820336 3.33594 0.742236 3.47656C0.658836 3.61719 0.617236 3.77083 0.617236 3.9375C0.617236 4.19271 0.705736 4.40625 0.882836 4.57812L6.83594 10.6641C6.94011 10.7682 7.04948 10.8463 7.16406 10.8984C7.27865 10.9505 7.40365 10.9766 7.53906 10.9766Z' fill='%23132E6B'/%3E%3C/svg%3E");
  }
}

</style>
