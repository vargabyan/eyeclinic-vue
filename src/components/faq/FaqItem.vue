<script setup>
import {ref} from 'vue'

const action = ref(false)

const handleOpen = () => {
  action.value = !action.value;
}

const {item} = defineProps(['item'])

</script>

<template>
  <div class="faq_content_item_subtitle-wrapper" :class="action ? 'open' : 'close'" @click="handleOpen">
    <strong class="faq_content_item_subtitle">{{ item.question }}</strong>
  </div>
  <p class="faq_content_item_text" :class=" action ? 'text-open' : 'text-close'">
    {{ item.answer }}
  </p>
</template>

<style scoped>

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

.faq_content_item_subtitle-wrapper {
  border-radius: 12px;
  padding: 20px;
  display: flex;
  gap: 8px;
  cursor: pointer;
}

.faq_content_item_subtitle-wrapper:before {
  content: '';
  display: list-item;
  List-style-type: decimal;
  font-size: 16px;
  font-weight: 500;
  margin-left: 20px;
}

.faq_content_item_subtitle-wrapper:after {
  display: block;
  content: '';
  max-width: 18px;
  width: 100%;
  height: 18px;
}

.open {
  background: var(--Primary);
  color: var(--White);
}

.close {
  background: rgba(229, 236, 240, 0.50);
  color: var(--Black);
}

.close:after {
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='18' height='19' viewBox='0 0 18 19' fill='none'%3E%3Cg clip-path='url(%23clip0_342_1855)'%3E%3Cpath d='M16.3929 8.2161H10.9286C10.7511 8.2161 10.6071 8.07218 10.6071 7.89467V2.43038C10.6071 1.54285 9.88754 0.823242 9 0.823242C8.11246 0.823242 7.39286 1.54285 7.39286 2.43038V7.89467C7.39286 8.07218 7.24894 8.2161 7.07143 8.2161H1.60714C0.719604 8.2161 0 8.9357 0 9.82324C0 10.7108 0.719604 11.4304 1.60714 11.4304H7.07143C7.24894 11.4304 7.39286 11.5743 7.39286 11.7518V17.2161C7.39286 18.1036 8.11246 18.8232 9 18.8232C9.88754 18.8232 10.6071 18.1036 10.6071 17.2161V11.7518C10.6071 11.5743 10.7511 11.4304 10.9286 11.4304H16.3929C17.2804 11.4304 18 10.7108 18 9.82324C18 8.9357 17.2804 8.2161 16.3929 8.2161Z' fill='%235AA9D4'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0_342_1855'%3E%3Crect width='18' height='18' fill='white' transform='translate(0 0.823242)'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E");
}

.open:after {
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='18' height='19' viewBox='0 0 18 19' fill='none'%3E%3Cg clip-path='url(%23clip0_342_1855)'%3E%3Cpath d='M16.3929 8.2161H10.9286C10.7511 8.2161 10.6071 8.07218 10.6071 7.89467V2.43038C10.6071 1.54285 9.88754 0.823242 9 0.823242C8.11246 0.823242 7.39286 1.54285 7.39286 2.43038V7.89467C7.39286 8.07218 7.24894 8.2161 7.07143 8.2161H1.60714C0.719604 8.2161 0 8.9357 0 9.82324C0 10.7108 0.719604 11.4304 1.60714 11.4304H7.07143C7.24894 11.4304 7.39286 11.5743 7.39286 11.7518V17.2161C7.39286 18.1036 8.11246 18.8232 9 18.8232C9.88754 18.8232 10.6071 18.1036 10.6071 17.2161V11.7518C10.6071 11.5743 10.7511 11.4304 10.9286 11.4304H16.3929C17.2804 11.4304 18 10.7108 18 9.82324C18 8.9357 17.2804 8.2161 16.3929 8.2161Z' fill='%23fff'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0_342_1855'%3E%3Crect width='18' height='18' fill='white' transform='translate(0 0.823242)'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E");
  transform: rotate(45deg);
}

.faq_content_item_subtitle {
  font-size: 16px;
  font-weight: 500;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.faq_content_item_text {
  color: var(--Black);
  font-size: 16px;
  line-height: 24px;
  padding: 30px 20px;
  box-shadow: 3px 3px 20px 0 rgba(90, 169, 213, 0.15);
}

.text-open {
  display: block;
}

.text-close {
  display: none;
}

@media (max-width: 768px) {

  .faq_content_item_subtitle-wrapper {
    border-radius: 0;
    padding: 20px 32px;
  }

  .faq_content_item_text {
    box-shadow: 3px 3px 20px 0 rgba(90, 169, 213, 0.15);
  }

  .faq_content_item_subtitle-wrapper:after {
    display: flex;
    align-self: center;
  }
}

</style>
