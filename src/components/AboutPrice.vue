<script setup>
import {ref} from 'vue'

const hiddenDescriptionText = ref(false)

const handleReadMore = () => {
  hiddenDescriptionText.value = !hiddenDescriptionText.value;
}
</script>

<template>
  <div class="about-price container-offset">
    <div class="about-price_header-wrapper">
      <div class="about-price_subtitle-wrapper">
        <h1 class="about-price_header">О центре</h1>
        <p class="about-price_subtitle">работаем с 1988 года</p>
      </div>
      <a class="about-price_detail" href="">Подробнее <span>о центре</span></a>
    </div>

    <div class="about-price_content-wrapper">
      <img class="about-price_img" src="/src/assets/images/image%2033.png" alt="">
      <button class="about-price_content_read-more" @click="handleReadMore">Читать дальше</button>
      <div class="about-price_description" :class="{'about-price_description-open': hiddenDescriptionText}">
        <p class="about-price_description_text">
          Екатеринбургский центре МНТК «Микрохирургия глаза» —один из самых крупных работающийх офтальмологический
          центров в Росcии, являющейся лучшей частной организацие в стране.
        </p>
        <p class="about-price_description_text">
          Клиника располагает мощной диагностической линией, оснащенными ультрасовременными технологиями операционными
          залами, прекрасным стационаром.
        </p>
        <p class="about-price_description_text">
          Специалисты Екатеринбургского центра МНТК "Микрохирургии глаза" - это профессионалы высокой квалификации,
          объединенные общей целью – возвращать зрение тысячам людей – и стремлением достичь успеха, быть лучшими в
          своей сфере. Консультирующие врачи центра - доктора и кандидаты медицинских наук, специалисты высшей
          категории. Специалистами Центра ведется научная деятельность, результат которой - более 178 собственных
          разработок, подтвержденных патентами Российской Федерации. На базе Центра регулярно проводятся международные и
          региональные конференции по офтальмологии.
        </p>
      </div>
    </div>

    <div class="about-price_footer">
      <div class="about-price_footer_items-wrapper">
        <div class="about-price_footer_item">
          <p class="about-price_footer_subtitle">более</p>
          <h1 class="about-price_count">1 миллиона</h1>
          <strong class="about-price_actions">Операций</strong>
        </div>
        <div class="about-price_footer_item">
          <p class="about-price_footer_subtitle">более</p>
          <h1 class="about-price_count">5 миллионов</h1>
          <strong class="about-price_actions">Пациентов прошли
            диагностическое обследование</strong>
        </div>
        <div class="about-price_footer_item">
          <p class="about-price_footer_subtitle">более</p>
          <h1 class="about-price_count">250 тысяч</h1>
          <strong class="about-price_actions">Человек ежегодно проходят обследование, получают лечение по самым
            передовым
            технологиям</strong>
        </div>
        <div class="about-price_footer_item">
          <p class="about-price_footer_subtitle">у центра</p>
          <h1 class="about-price_count">12</h1>
          <strong class="about-price_actions">международных наград</strong>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

.about-price {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.about-price_header-wrapper {
  display: flex;
  justify-content: space-between;
}

.about-price_subtitle-wrapper {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.about-price_header {
  color: var(--Main);
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.64px;
}

.about-price_subtitle {
  color: var(--Text-2);
  font-size: 16px;
  font-weight: 500;
}

.about-price_detail {
  display: flex;
  padding: 8px 14px;
  justify-content: center;
  align-items: flex-start;
  gap: 4px;
  border-radius: 8px;
  background: rgba(229, 236, 240, 0.50);
  color: var(--Main);
  font-size: 14px;
  font-weight: 500;
  letter-spacing: -0.28px;
  height: max-content;
}

.about-price_content-wrapper {
  display: flex;
  gap: 50px;
  justify-content: space-between;
}

.about-price_img {
  max-width: 440px;
  width: 100%;
  max-height: 380px;
  flex-shrink: 0;
  border-radius: 13px;
}

.about-price_content_read-more {
  display: none;
  color: var(--Primary);
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
  text-transform: uppercase;
}

.about-price_description {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.about-price_description_text {
  color: var(--Text-2);
  font-size: 16px;
  line-height: 24px;
}

.about-price_footer {
  display: flex;
  flex-direction: column;
}

.about-price_footer_items-wrapper {
  display: flex;
  gap: 16px;
}

.about-price_footer_item {
  display: flex;
  min-height: 161px;
  padding: 20px;
  flex-direction: column;
  align-items: flex-start;
  gap: 10px;
  flex: 1 0 0;
  border-radius: 10px;
  background: var(--Tretiary);
}

.about-price_footer_item:nth-child(1) {
  max-width: 228px;
}

.about-price_footer_item:nth-child(2) {
  max-width: 228px;
}

.about-price_footer_item:nth-child(3) {
  max-width: 296px;
}

.about-price_footer_item:nth-child(4) {
  max-width: 160px;
  background-image: url('/src/assets/images/Frame 2087324979.png');
  background-repeat: no-repeat;
  background-position: bottom right;
}

.about-price_footer_subtitle {
  color: var(--Text);
  font-size: 11px;
  font-weight: 700;
  line-height: 16px;
  text-transform: uppercase;
}

.about-price_count {
  color: var(--Main);
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.64px;
}

.about-price_actions {
  color: var(--Main);
  font-size: 12px;
  font-weight: 700;
  line-height: 16px;
  text-transform: uppercase;
}


@media (max-width: 768px) {
  .about-price {
    gap: 20px;
  }

  .about-price_subtitle-wrapper {
    gap: 6px;
  }

  .about-price_header {
    font-size: 28px;
    letter-spacing: -0.56px;
  }

  .about-price_subtitle {
    font-size: 16px;
  }

  .about-price_detail {
    display: flex;
    padding: 8px 14px;
    justify-content: center;
    align-items: flex-start;
    gap: 10px;
    border-radius: 8px;
    background: rgba(229, 236, 240, 0.50);
    color: var(--Main);
    font-size: 14px;
    font-weight: 500;
    letter-spacing: -0.28px;
    height: max-content;
  }

  .about-price_detail span {
    display: none;
  }

  .about-price_content-wrapper {
    gap: 20px;
    flex-direction: column-reverse;
  }

  .about-price_description {
    height: 144px;
    overflow: hidden;
  }

  .about-price_description-open {
    height: 100%;
  }

  .about-price_content_read-more {
    display: flex;
  }

  .about-price_img {
    max-height: 245px;
  }

  .about-price_footer {
    gap: 20px;
  }

  .about-price_footer:before {
    display: block;
    content: '';
    width: 78px;
    height: 21px;
    background-image: url("data:image/svg+xml,%3Csvg width='79' height='23' viewBox='0 0 79 23' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M17 11.9414V8.44141C17 7.61341 16.329 6.94141 15.5 6.94141V6.94141C14.672 6.94141 14 7.61341 14 8.44141' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M17 9.44141C17 8.61341 17.672 7.94141 18.5 7.94141V7.94141C19.329 7.94141 20 8.61341 20 9.44141V12.9414' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M14.0012 11.9414V3.44141C14.0012 2.61341 13.3302 1.94141 12.5012 1.94141V1.94141C11.6732 1.94141 11.0012 2.61341 11.0012 3.44141V10.9414V13.9414L9.11718 12.0574C8.50018 11.4404 7.50118 11.4404 6.88418 12.0574V12.0574C6.37018 12.5714 6.29018 13.3764 6.69418 13.9814L10.2202 19.2694C11.3332 20.9384 13.2062 21.9414 15.2132 21.9414H17.0012C20.3152 21.9414 23.0012 19.2554 23.0012 15.9414V11.9414V10.4414C23.0012 9.61341 22.3302 8.94141 21.5012 8.94141V8.94141C20.6732 8.94141 20.0012 9.61341 20.0012 10.4414' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M23.0857 1L24.9997 2.914L22.9727 4.941' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M2.91434 1L1.00034 2.914L3.02734 4.941' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M25 2.91113H19' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M1 2.91113H7' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M44.8774 16.4707H43.7349V8.33936H40.3896L40.0977 13.043C40.0215 14.2617 39.7972 15.1483 39.4248 15.7026C39.0566 16.2528 38.5023 16.5278 37.7617 16.5278C37.5924 16.5278 37.4443 16.5067 37.3174 16.4644V15.4424C37.4105 15.4678 37.5247 15.4805 37.6602 15.4805C38.096 15.4805 38.4176 15.2879 38.625 14.9028C38.8366 14.5177 38.9678 13.883 39.0186 12.9985L39.3486 7.31104H44.8774V16.4707ZM47.7021 16.4707H46.6104V9.86914H47.7021V14.7822H47.7529L51.0537 9.86914H52.1455V16.4707H51.0537V11.5576H51.0029L47.7021 16.4707ZM59.1597 11.9004H58.0679C57.9663 11.5576 57.7738 11.2762 57.4902 11.0562C57.2067 10.8361 56.8449 10.7261 56.4048 10.7261C55.8293 10.7261 55.368 10.9504 55.021 11.3989C54.674 11.8433 54.5005 12.4336 54.5005 13.1699C54.5005 13.9189 54.674 14.5135 55.021 14.9536C55.3722 15.3937 55.8377 15.6138 56.4175 15.6138C56.8491 15.6138 57.2067 15.5122 57.4902 15.3091C57.778 15.106 57.9748 14.8203 58.0806 14.4521H59.1724C59.0623 15.0869 58.7576 15.6011 58.2583 15.9946C57.759 16.3882 57.1432 16.585 56.4111 16.585C55.4886 16.585 54.7523 16.2782 54.2021 15.6646C53.652 15.0467 53.377 14.2152 53.377 13.1699C53.377 12.1416 53.652 11.3164 54.2021 10.6943C54.7523 10.068 55.4844 9.75488 56.3984 9.75488C57.1559 9.75488 57.778 9.96224 58.2646 10.377C58.7555 10.7917 59.0539 11.2995 59.1597 11.9004ZM65.0249 9.86914V10.7769H62.8921V16.4707H61.8003V10.7769H59.6675V9.86914H65.0249ZM67.9766 15.6455C68.4971 15.6455 68.9329 15.4847 69.2842 15.1631C69.6396 14.8372 69.8174 14.4373 69.8174 13.9634V13.4238L68.0527 13.5317C67.6084 13.5614 67.2635 13.6693 67.0181 13.8555C66.7769 14.0417 66.6562 14.2913 66.6562 14.6045C66.6562 14.9176 66.7769 15.1694 67.0181 15.3599C67.2593 15.5503 67.5788 15.6455 67.9766 15.6455ZM67.729 16.585C67.0731 16.585 66.542 16.403 66.1357 16.0391C65.7337 15.6751 65.5327 15.1969 65.5327 14.6045C65.5327 14.0374 65.7401 13.5846 66.1548 13.2461C66.5737 12.9076 67.1641 12.7171 67.9258 12.6748L69.8174 12.5669V12.0146C69.8174 11.6126 69.6904 11.2974 69.4365 11.0688C69.1826 10.8403 68.8271 10.7261 68.3701 10.7261C67.9512 10.7261 67.6105 10.8192 67.3481 11.0054C67.0858 11.1873 66.9186 11.4434 66.8467 11.7734H65.7803C65.8184 11.1852 66.0723 10.7028 66.542 10.3262C67.016 9.94531 67.6338 9.75488 68.3955 9.75488C69.1699 9.75488 69.7835 9.94954 70.2363 10.3389C70.6934 10.7282 70.9219 11.2508 70.9219 11.9067V16.4707H69.8745V15.3345H69.8491C69.6502 15.7111 69.3582 16.0137 68.9731 16.2422C68.5881 16.4707 68.1733 16.585 67.729 16.585ZM73.5371 16.4707H72.4453V9.86914H73.5371V14.7822H73.5879L76.8887 9.86914H77.9805V16.4707H76.8887V11.5576H76.8379L73.5371 16.4707ZM73.2896 7.0127H74.1021C74.1021 7.38932 74.2142 7.70247 74.4385 7.95215C74.667 8.20182 74.9653 8.32666 75.3335 8.32666C75.7017 8.32666 75.9979 8.20182 76.2222 7.95215C76.4507 7.70247 76.5649 7.38932 76.5649 7.0127H77.3774C77.3774 7.59668 77.187 8.07064 76.8062 8.43457C76.4295 8.7985 75.9386 8.98047 75.3335 8.98047C74.7284 8.98047 74.2354 8.7985 73.8545 8.43457C73.4779 8.07064 73.2896 7.59668 73.2896 7.0127Z' fill='%23B2B2B2'/%3E%3C/svg%3E%0A");
  }

  .about-price_footer_items-wrapper {
    overflow: scroll;
  }

  .about-price_footer_items-wrapper::-webkit-scrollbar {
    display: none;
  }

  .about-price_footer_item:nth-child(1) {
    min-width: 228px;
  }

  .about-price_footer_item:nth-child(2) {
    min-width: 228px;
  }

  .about-price_footer_item:nth-child(3) {
    min-width: 296px;
  }

  .about-price_footer_item:nth-child(4) {
    min-width: 160px;
  }

}

</style>