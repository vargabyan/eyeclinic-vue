<script setup>
import {onMounted, ref} from 'vue'
import ReviewsItem from '/src/components/reviews/ReviewsItems.vue'
import Swiper from 'https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.mjs'

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
    review: 'В целом от Екатеринбургский центр МНТК «Микрохирургия глаза» на Ясной,31 остались только положительные эмоции. Все сотрудники обходительные, вежливые, помещение чистое и очень приятное.Мне делали лазерную операцию по укреплению сетчатки (если говорить простым языком), и очень хочется поблагодарить замечательного специалиста Степанова , и очень хочется поблагодарить замечательного специалиста Степанова...',
    date: '26 июня 2021',
  }
]

onMounted(() => {

  new Swiper('.reviews-swiper', {

    navigation: {
      nextEl: '.swiper-button-next',
      prevEl: '.swiper-button-prev',
    },

    spaceBetween: 20,
    slidesPerView: 1,
  });
})

const windowWidth = ref(window.innerWidth >= 768)

window.addEventListener('resize', () => {
  windowWidth.value = window.innerWidth >= 768
})

</script>

<template>
  <div class="reviews container-offset">
    <div class="reviews_header-wrapper">
      <h1 class="reviews_header">Отзывы</h1>
      <a class="reviews_view-all" href="" v-show="windowWidth">Посмотреть все</a>
    </div>
    <div class="reviews_item-wrapper">
      <div class="reviews_item" v-show="windowWidth" v-for="reviewsItem in responseData">
        <ReviewsItem v-bind:reviewsItem="reviewsItem"/>
      </div>

      <div class="swiper reviews-swiper" v-show="!windowWidth">
        <div class="swiper-wrapper">
          <div class="swiper-slide reviews_item" v-for="reviewsItem in responseData">
            <ReviewsItem v-bind:reviewsItem="reviewsItem"/>
          </div>
        </div>
      </div>
      <div class="swiper-button-prev" v-show="!windowWidth"></div>
      <div class="swiper-button-next" v-show="!windowWidth"></div>

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
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  position: relative;
}

.reviews_item {
  display: flex;
  padding: 30px;
  flex-direction: column;
  gap: 10px;
}

@media (max-width: 992px) {
  .reviews_item {
    padding: 0;
  }
}

@media (max-width: 768px) {

  .reviews {
    background: unset;
  }

  .reviews_header {
    color: var(--Main);
    font-size: 28px;
    letter-spacing: -0.56px;
  }

  .reviews_item-wrapper {
    display: flex;
    border-radius: 10px;
    background: #FFF;
    padding: 24px;
  }

  .swiper-button-prev,
  .swiper-button-next {
    position: absolute;
  }

  .swiper-button-prev:after,
  .swiper-button-next:after {
    display: block;
    content: '';
    width: 8px;
    height: 15px;
  }

  .swiper-button-prev {
    left: -1px;
  }

  .swiper-button-next {
    right: -1px;
  }

  .swiper-button-prev:after {
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='8' height='15' viewBox='0 0 8 15' fill='none'%3E%3Cpath d='M0 7.4958C0 7.34898 0.0261941 7.21347 0.0785809 7.08925C0.130978 6.96501 0.209558 6.84644 0.314342 6.73351L6.43615 0.279505C6.60904 0.0931686 6.82384 0 7.08055 0C7.2482 0 7.40275 0.0451728 7.5442 0.135517C7.68566 0.220216 7.7983 0.33597 7.88212 0.48278C7.96071 0.629589 8 0.796166 8 0.982497C8 1.24788 7.9057 1.48504 7.71709 1.69396L2.20039 7.4958L7.71709 13.2976C7.9057 13.5065 8 13.7465 8 14.0176C8 14.1983 7.96071 14.362 7.88212 14.5088C7.7983 14.6613 7.68566 14.7798 7.5442 14.8645C7.40275 14.9549 7.2482 15 7.08055 15C6.82384 15 6.60904 14.9041 6.43615 14.7121L0.314342 8.25808C0.209558 8.14514 0.130978 8.02657 0.0785809 7.90235C0.0261941 7.77812 0 7.6426 0 7.4958Z' fill='%235C6884'/%3E%3C/svg%3E");
  }

  .swiper-button-next:after {
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='8' height='15' viewBox='0 0 8 15' fill='none'%3E%3Cpath d='M8 7.4958C8 7.34898 7.97381 7.21347 7.92142 7.08925C7.86902 6.96501 7.79044 6.84644 7.68566 6.73351L1.56385 0.279505C1.39096 0.0931686 1.17616 0 0.91945 0C0.751801 0 0.59725 0.0451728 0.455795 0.135517C0.314342 0.220216 0.201702 0.33597 0.117878 0.48278C0.0392927 0.629589 0 0.796166 0 0.982497C0 1.24788 0.0943031 1.48504 0.282908 1.69396L5.79961 7.4958L0.282908 13.2976C0.0943031 13.5065 0 13.7465 0 14.0176C0 14.1983 0.0392927 14.362 0.117878 14.5088C0.201702 14.6613 0.314342 14.7798 0.455795 14.8645C0.59725 14.9549 0.751801 15 0.91945 15C1.17616 15 1.39096 14.9041 1.56385 14.7121L7.68566 8.25808C7.79044 8.14514 7.86902 8.02657 7.92142 7.90235C7.97381 7.77812 8 7.6426 8 7.4958Z' fill='%235C6884'/%3E%3C/svg%3E");
  }
}

</style>
