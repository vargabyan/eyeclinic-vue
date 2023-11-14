<script setup>

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

const printGrade = (grades) => {
  const stars = [1, 2, 3, 4, 5];

  return stars.map(star => {
    if (star <= grades) {
      return '<div class="reviews_item_grade-is"></div>'
    } else {
      return '<div class="reviews_item_grade-not"></div>'
    }
  })
}

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
          <div class="reviews_item_grades" v-for="item in printGrade(reviewsItem.grade)">
<!--            {{ item }}-->
          </div>
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

.reviews_item_grade-is,
.reviews_item_grade-not {
  display: block;
  width: 20px;
  height: 20px;
}

.reviews_item_grade-is {
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20' height='21' viewBox='0 0 20 21' fill='none'%3E%3Cg clip-path='url(%23clip0_320_2069)'%3E%3Cpath d='M10.9655 1.8602L13.2213 6.43092C13.3781 6.74881 13.6814 6.96909 14.0323 7.01999L19.0765 7.75299C19.9601 7.88148 20.3126 8.967 19.6735 9.58987L16.0235 13.1476C15.7699 13.395 15.6539 13.7517 15.714 14.1009L16.5755 19.1247C16.7265 20.0046 15.8028 20.6754 15.0127 20.2603L10.5012 17.8886C10.1875 17.7238 9.81243 17.7238 9.4987 17.8886L4.98723 20.2603C4.19708 20.6758 3.27342 20.0046 3.42444 19.1247L4.28594 14.1009C4.34601 13.7517 4.23003 13.395 3.97638 13.1476L0.326404 9.58987C-0.312728 8.96659 0.0397958 7.88106 0.9234 7.75299L5.96762 7.01999C6.31848 6.96909 6.62177 6.74881 6.77864 6.43092L9.03437 1.8602C9.42903 1.05962 10.5705 1.05962 10.9655 1.8602Z' fill='%23FF8D76'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0_320_2069'%3E%3Crect width='20' height='20' fill='white' transform='translate(0 0.823242)'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E");
}

.reviews_item_grade-not {
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20' height='21' viewBox='0 0 20 21' fill='none'%3E%3Cg clip-path='url(%23clip0_320_2069)'%3E%3Cpath d='M10.9655 1.8602L13.2213 6.43092C13.3781 6.74881 13.6814 6.96909 14.0323 7.01999L19.0765 7.75299C19.9601 7.88148 20.3126 8.967 19.6735 9.58987L16.0235 13.1476C15.7699 13.395 15.6539 13.7517 15.714 14.1009L16.5755 19.1247C16.7265 20.0046 15.8028 20.6754 15.0127 20.2603L10.5012 17.8886C10.1875 17.7238 9.81243 17.7238 9.4987 17.8886L4.98723 20.2603C4.19708 20.6758 3.27342 20.0046 3.42444 19.1247L4.28594 14.1009C4.34601 13.7517 4.23003 13.395 3.97638 13.1476L0.326404 9.58987C-0.312728 8.96659 0.0397958 7.88106 0.9234 7.75299L5.96762 7.01999C6.31848 6.96909 6.62177 6.74881 6.77864 6.43092L9.03437 1.8602C9.42903 1.05962 10.5705 1.05962 10.9655 1.8602Z' fill='%23DEE8EE'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0_320_2069'%3E%3Crect width='20' height='20' fill='white' transform='translate(0 0.823242)'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E");
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
