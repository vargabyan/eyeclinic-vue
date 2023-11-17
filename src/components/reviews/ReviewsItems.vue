<script setup>
import ReviewsGrades from '/src/components/reviews/ReviewsGrades.vue'
import {ref} from "vue";

const {reviewsItem} = defineProps(['reviewsItem'])
const handle = ref(false)
const windowWidth = ref(window.innerWidth >= 768)
const buttonText = ref(windowWidth.value ? 'Показать целиком' : 'Посмотреть Все')

const handleOpen = () => {
  handle.value = !handle.value
}

window.addEventListener('resize', () => {
  windowWidth.value = window.innerWidth >= 768

  buttonText.value = windowWidth.value ? 'Показать целиком' : 'Посмотреть Все'
})


</script>

<template>
  <div class="reviews_item_header-wrapper">
    <strong class="reviews_item_name">
      {{ reviewsItem.name }}
      <span class="reviews_item_job-title" v-show="windowWidth">{{ reviewsItem.jubTitle }}</span>
    </strong>
    <ReviewsGrades v-bind:grade="reviewsItem.grade"/>
  </div>
  <p class="reviews_item_text" :class="handle ? 'text-open' : 'text-close'">
    {{ reviewsItem.review }}
  </p>
  <div class="reviews_item_footer-wrapper">
    <button class="reviews_item_view-all" @click="handleOpen">{{ buttonText }}</button>
    <p class="reviews_item_date" v-show="windowWidth">{{ reviewsItem.date }}</p>
  </div>
</template>

<style scoped>

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

.reviews_item_text {
  color: var(--Black);
  font-size: 16px;
  line-height: 24px;
  overflow: hidden;
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

.text-open {
  height: 100%;
}

.text-close {
  height: 144px;
}

</style>
