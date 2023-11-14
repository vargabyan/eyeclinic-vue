<script setup>
import ReviewsItem from '/src/components/reviews/ReviewsItem.vue'

const responseData = [
  {
    name: 'Макаров Антон',
    jubTitle: 'Первое хирургическое отделение',
    grade: 5,
    review: 'В целом от Екатеринбургский центр МНТК «Микрохирургия глаза» на Ясной,31 остались только положительные эмоции. Все сотрудники обходительные, вежливые, помещение чистое и очень приятное.Мне делали лазерную операцию по укреплению сетчатки (если говорить простым языком), и очень хочется поблагодарить замечательного специалиста Степанова...',
    date: '26 июня 2021',
  },
  {
    name: 'Макаров Антон',
    jubTitle: 'Первое хирургическое отделение',
    grade: 4,
    review: 'В целом от Екатеринбургский центр МНТК «Микрохирургия глаза» на Ясной,31 остались только положительные эмоции. Все сотрудники обходительные, вежливые, помещение чистое и очень приятное.Мне делали лазерную операцию по укреплению сетчатки (если говорить простым языком), и очень хочется поблагодарить замечательного специалиста Степанова...',
    date: '26 июня 2021',
  }
]

</script>

<template>
  <div class="reviews container-offset">
    <div class="reviews_header-wrapper">
      <h1 class="reviews_header">Отзывы</h1>
      <a class="reviews_view-all" href="">Посмотреть все</a>
    </div>
    <div class="reviews_item-wrapper">
      <div class="reviews_item" v-for="reviewsItem in responseData">
        <div class="reviews_item_header-wrapper">
          <strong class="reviews_item_name">
            {{ reviewsItem.name }}
            <span class="reviews_item_job-title">{{ reviewsItem.jubTitle }}</span>
          </strong>
          <ReviewsItem v-bind:grade="reviewsItem.grade"/>
        </div>
        <p class="reviews_item_text">
          {{ reviewsItem.review }}
        </p>
        <div class="reviews_item_footer-wrapper">
          <button class="reviews_item_view-all">Показать целиком</button>
          <p class="reviews_item_date">{{ reviewsItem.date }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

.reviews {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.reviews_header-wrapper {
  display: flex;
  justify-content: space-between;
  align-self: stretch;
  gap: 32px;
}

.reviews_header {
  color: var(--Text-Heading);
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.64px;
}

.reviews_view-all {
  display: flex;
  padding: 8px 14px;
  justify-content: center;
  gap: 10px;
  border-radius: 8px;
  background: rgba(229, 236, 240, 0.50);
  color: var(--Main);
  font-size: 14px;
  font-weight: 500;
  letter-spacing: -0.28px;
}

.reviews_item-wrapper {
  display: flex;
  gap: 20px;
}

.reviews_item {
  display: flex;
  padding: 30px;
  flex-direction: column;
  gap: 10px;
}

.reviews_item_header-wrapper {
  display: flex;
  justify-content: space-between;
  gap: 30px;
}

.reviews_item_name {
  color: var(--Black);
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
  text-transform: uppercase;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.reviews_item_name span {
  color: var(--Text-2);
  font-size: 14px;
  font-weight: 400;
  letter-spacing: -0.28px;
  text-transform: none;
}

.reviews_item_grades {
  display: flex;
  gap: 6px;
}

.reviews_item_text {
  color: var(--Black);
  font-size: 16px;
  line-height: 24px;
}

.reviews_item_footer-wrapper {
  display: flex;
  justify-content: space-between;
  gap: 10px;
}

.reviews_item_view-all {
  color: var(--Primary);
  font-family: TT Norms;
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
  text-transform: uppercase;
}

.reviews_item_date {
  color: var(--Text);
  font-size: 14px;
  letter-spacing: -0.28px;
}

</style>
