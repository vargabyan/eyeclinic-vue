<script setup>
import {ref} from 'vue'

const responseData = [
  {
    status: 'Оснащение',
    title: 'Современное оснащение',
    text: 'Клиника располагает мощной диагностической линией, оснащенными ультрасовременными технологиями операционными залами, прекрасным стационаром.В настоящее время в Екатеринбурге работают: два отделения охраны детского зрения, Центр рефракционно-лазерной хирургии, городское отделение диагностики и лечения глаукомы, оптический салон.',
    img: '/src/assets/images/image%2034.png',
  },
  {
    status: 'Скорость',
    title: 'Скорость',
    text: 'Клиника располагает мощной диагностической линией,операционными залами, прекрасным стационаром.В настоящее время в Екатеринбурге работают: два отделения охраны детского зрения, Центр рефракционно-лазерной хирургии, городское отделение диагностики и лечения глаукомы, оптический салон.',
    img: '/src/assets/images/image%2034.png',
  },
  {
    status: 'Эффективность',
    title: 'Эффективность',
    text: 'Клиника располагает мощной диагностической линией, оснащенными ультрасовременными технологиями операционными залами, прекрасным стационаром.В настоящее время в Екатеринбурге работают: два отделения охраны детского зрения, Центр рефракционно-лазерной хирургии, городское отделение диагностики и лечения глаукомы, оптический салон.',
    img: '/src/assets/images/image%2034.png',
  },
]

const count = ref(0)
const windowWidth = ref(window.innerWidth > 768)

window.addEventListener('resize', () => {
  windowWidth.value = window.innerWidth > 768
})

const handleClick = (e) => {
  const {id} = e.target

  count.value = +id
}

</script>

<template>
  <div class="possibilities container-offset">
    <h1 class="possibilities_header">Возможности</h1>
    <div class="possibilities_scroll-through" v-show="!windowWidth"></div>
    <div class="possibilities_content" v-show="windowWidth">
      <div class="possibilities_description">
        <div class="possibilities_teg-wrapper">
          <button class="possibilities_tag-item" :class="{'possibilities_tag-item-active': (count === index)}"
                  @click="handleClick"
                  v-for="(item, index) in responseData" :id="index">{{ item.status }}
          </button>
        </div>
        <div class="possibilities_counter-wrapper">
          <p class="possibilities_counter">{{ count + 1 }}/<span>3</span></p>
        </div>
        <div class="possibilities_tex-wrapper">
          <h2 class="possibilities_test-header">{{ responseData[count].title }}</h2>
          <p class="possibilities_text">
            {{ responseData[count].text }}
          </p>
        </div>
      </div>
      <img class="possibilities_img" :src="responseData[count].img" alt="">
    </div>

    <div class="possibilities_content-mobile-item-wrapper">
      <div class="possibilities_content-mobile-item" v-show="!windowWidth" v-for="item in responseData">
        <div class="possibilities_description">
          <div class="possibilities_tex-wrapper">
            <h2 class="possibilities_test-header">{{ item.title }}</h2>
            <p class="possibilities_text">
              {{ item.text }}
            </p>
          </div>
        </div>
        <img class="possibilities_img" :src="item.img" alt="">
      </div>
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
  background-size: cover;
}

@media (max-width: 992px) {

  .possibilities_img {
    max-width: clamp(278px, 43vw, 502px);
  }
}

@media (max-width: 992px) {

  .possibilities_content {
    flex-direction: column;
  }

  .possibilities_img {
    max-width: 502px;
  }

}

@media (max-width: 768px) {

  .possibilities {
    gap: 20px;
  }

  .possibilities_header {
    color: var(--Main);
    font-size: 28px;
    letter-spacing: -0.56px;
  }

  .possibilities_scroll-through {
    display: block;
    content: '';
    width: 78px;
    height: 21px;
    background-image: url("data:image/svg+xml,%3Csvg width='79' height='23' viewBox='0 0 79 23' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M17 11.9414V8.44141C17 7.61341 16.329 6.94141 15.5 6.94141V6.94141C14.672 6.94141 14 7.61341 14 8.44141' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M17 9.44141C17 8.61341 17.672 7.94141 18.5 7.94141V7.94141C19.329 7.94141 20 8.61341 20 9.44141V12.9414' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M14.0012 11.9414V3.44141C14.0012 2.61341 13.3302 1.94141 12.5012 1.94141V1.94141C11.6732 1.94141 11.0012 2.61341 11.0012 3.44141V10.9414V13.9414L9.11718 12.0574C8.50018 11.4404 7.50118 11.4404 6.88418 12.0574V12.0574C6.37018 12.5714 6.29018 13.3764 6.69418 13.9814L10.2202 19.2694C11.3332 20.9384 13.2062 21.9414 15.2132 21.9414H17.0012C20.3152 21.9414 23.0012 19.2554 23.0012 15.9414V11.9414V10.4414C23.0012 9.61341 22.3302 8.94141 21.5012 8.94141V8.94141C20.6732 8.94141 20.0012 9.61341 20.0012 10.4414' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M23.0857 1L24.9997 2.914L22.9727 4.941' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M2.91434 1L1.00034 2.914L3.02734 4.941' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M25 2.91113H19' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M1 2.91113H7' stroke='%23788084' stroke-linecap='round' stroke-linejoin='round'/%3E%3Cpath d='M44.8774 16.4707H43.7349V8.33936H40.3896L40.0977 13.043C40.0215 14.2617 39.7972 15.1483 39.4248 15.7026C39.0566 16.2528 38.5023 16.5278 37.7617 16.5278C37.5924 16.5278 37.4443 16.5067 37.3174 16.4644V15.4424C37.4105 15.4678 37.5247 15.4805 37.6602 15.4805C38.096 15.4805 38.4176 15.2879 38.625 14.9028C38.8366 14.5177 38.9678 13.883 39.0186 12.9985L39.3486 7.31104H44.8774V16.4707ZM47.7021 16.4707H46.6104V9.86914H47.7021V14.7822H47.7529L51.0537 9.86914H52.1455V16.4707H51.0537V11.5576H51.0029L47.7021 16.4707ZM59.1597 11.9004H58.0679C57.9663 11.5576 57.7738 11.2762 57.4902 11.0562C57.2067 10.8361 56.8449 10.7261 56.4048 10.7261C55.8293 10.7261 55.368 10.9504 55.021 11.3989C54.674 11.8433 54.5005 12.4336 54.5005 13.1699C54.5005 13.9189 54.674 14.5135 55.021 14.9536C55.3722 15.3937 55.8377 15.6138 56.4175 15.6138C56.8491 15.6138 57.2067 15.5122 57.4902 15.3091C57.778 15.106 57.9748 14.8203 58.0806 14.4521H59.1724C59.0623 15.0869 58.7576 15.6011 58.2583 15.9946C57.759 16.3882 57.1432 16.585 56.4111 16.585C55.4886 16.585 54.7523 16.2782 54.2021 15.6646C53.652 15.0467 53.377 14.2152 53.377 13.1699C53.377 12.1416 53.652 11.3164 54.2021 10.6943C54.7523 10.068 55.4844 9.75488 56.3984 9.75488C57.1559 9.75488 57.778 9.96224 58.2646 10.377C58.7555 10.7917 59.0539 11.2995 59.1597 11.9004ZM65.0249 9.86914V10.7769H62.8921V16.4707H61.8003V10.7769H59.6675V9.86914H65.0249ZM67.9766 15.6455C68.4971 15.6455 68.9329 15.4847 69.2842 15.1631C69.6396 14.8372 69.8174 14.4373 69.8174 13.9634V13.4238L68.0527 13.5317C67.6084 13.5614 67.2635 13.6693 67.0181 13.8555C66.7769 14.0417 66.6562 14.2913 66.6562 14.6045C66.6562 14.9176 66.7769 15.1694 67.0181 15.3599C67.2593 15.5503 67.5788 15.6455 67.9766 15.6455ZM67.729 16.585C67.0731 16.585 66.542 16.403 66.1357 16.0391C65.7337 15.6751 65.5327 15.1969 65.5327 14.6045C65.5327 14.0374 65.7401 13.5846 66.1548 13.2461C66.5737 12.9076 67.1641 12.7171 67.9258 12.6748L69.8174 12.5669V12.0146C69.8174 11.6126 69.6904 11.2974 69.4365 11.0688C69.1826 10.8403 68.8271 10.7261 68.3701 10.7261C67.9512 10.7261 67.6105 10.8192 67.3481 11.0054C67.0858 11.1873 66.9186 11.4434 66.8467 11.7734H65.7803C65.8184 11.1852 66.0723 10.7028 66.542 10.3262C67.016 9.94531 67.6338 9.75488 68.3955 9.75488C69.1699 9.75488 69.7835 9.94954 70.2363 10.3389C70.6934 10.7282 70.9219 11.2508 70.9219 11.9067V16.4707H69.8745V15.3345H69.8491C69.6502 15.7111 69.3582 16.0137 68.9731 16.2422C68.5881 16.4707 68.1733 16.585 67.729 16.585ZM73.5371 16.4707H72.4453V9.86914H73.5371V14.7822H73.5879L76.8887 9.86914H77.9805V16.4707H76.8887V11.5576H76.8379L73.5371 16.4707ZM73.2896 7.0127H74.1021C74.1021 7.38932 74.2142 7.70247 74.4385 7.95215C74.667 8.20182 74.9653 8.32666 75.3335 8.32666C75.7017 8.32666 75.9979 8.20182 76.2222 7.95215C76.4507 7.70247 76.5649 7.38932 76.5649 7.0127H77.3774C77.3774 7.59668 77.187 8.07064 76.8062 8.43457C76.4295 8.7985 75.9386 8.98047 75.3335 8.98047C74.7284 8.98047 74.2354 8.7985 73.8545 8.43457C73.4779 8.07064 73.2896 7.59668 73.2896 7.0127Z' fill='%23B2B2B2'/%3E%3C/svg%3E%0A");
  }

  .possibilities_content-mobile-item-wrapper {
    display: flex;
    gap: 20px;
    overflow-x: scroll;
  }

  .possibilities_content-mobile-item-wrapper::-webkit-scrollbar {
    display: none;
  }

  .possibilities_content-mobile-item {
    min-width: 278px;
    width: 100%;
    display: flex;
    flex-direction: column-reverse;
    justify-content: flex-end;
    gap: 24px;

    padding: 20px;
    border-radius: 10px;
    box-shadow: 3px 3px 20px 0 rgba(90, 169, 213, 0.15);
    margin: 6px 6px 23px 6px;
  }

  .possibilities_description {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .possibilities_tex-wrapper {
    gap: 16px;
  }

  .possibilities_test-header {
    color: var(--Black);
    font-size: 16px;
    line-height: 20px;
  }

  .possibilities_text {
    line-height: 24px;
  }

  .possibilities_img {
    border-radius: 10px;
  }
}

</style>