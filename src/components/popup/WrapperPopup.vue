<script setup>
import {onUpdated, ref} from 'vue'

const {handelPopup} = defineProps(['handelPopup'])
const coordinateWrapperPopup = ref('0')

onUpdated(() => {
  const posTop = Math.round(window.scrollY);
  coordinateWrapperPopup.value = `${posTop}px`

  const body = document.querySelector('body')
  handelPopup.popupStatus ? body.style['overflow'] = 'hidden' : body.style['overflow'] = 'unset'
})

const handleClose = () => {
  handelPopup.popupStatus = !handelPopup.popupStatus
}

</script>

<template>
  <div class="wrapper-popup_background" v-show="handelPopup.popupStatus">
    <div class="wrapper-popup">
      <button class="wrapper-popup_closet" @click="handleClose">Закрыть</button>
      <div class="wrapper-popup_items-wrapper">
        <slot/>
      </div>
    </div>
  </div>
</template>

<style scoped>

.wrapper-popup_background {
  position: absolute;
  width: 100vw;
  height: 100vh;
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.20) 0%, rgba(0, 0, 0, 0.20) 100%);
  top: v-bind(coordinateWrapperPopup);
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: center;
}

.wrapper-popup {
  display: flex;
  align-items: center;
  padding: 30px 30px 70px 30px;
  flex-direction: column;
  gap: 23px;
  border-radius: 10px;
  background: #FFF;
  max-width: 448px;
  width: 100%;
  margin-top: 137px;
  height: min-content;
}

.wrapper-popup_closet {
  color: var(--Main);
  font-size: 14px;
  letter-spacing: -0.28px;
  display: flex;
  align-items: center;
  align-self: self-end;
  gap: 8px;
}

.wrapper-popup_closet:before {
  display: block;
  content: '';
  width: 12px;
  height: 12px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='13' viewBox='0 0 12 13' fill='none'%3E%3Cpath d='M6.66295 6.5049L11.8627 1.30511C12.0458 1.12204 12.0458 0.825232 11.8627 0.642185C11.6796 0.459139 11.3828 0.459115 11.1998 0.642185L5.99999 5.84197L0.800231 0.642185C0.617161 0.459115 0.320349 0.459115 0.137302 0.642185C-0.0457441 0.825255 -0.0457675 1.12207 0.137302 1.30511L5.33707 6.50488L0.137302 11.7047C-0.0457675 11.8877 -0.0457675 12.1845 0.137302 12.3676C0.228826 12.4591 0.348802 12.5049 0.468778 12.5049C0.588755 12.5049 0.708708 12.4591 0.800254 12.3676L5.99999 7.16783L11.1998 12.3676C11.2913 12.4591 11.4113 12.5049 11.5312 12.5049C11.6512 12.5049 11.7712 12.4591 11.8627 12.3676C12.0458 12.1845 12.0458 11.8877 11.8627 11.7047L6.66295 6.5049Z' fill='%23132E6B'/%3E%3C/svg%3E");
}

.wrapper-popup_items-wrapper {
  display: flex;
  padding: 0 33px;
  flex-direction: column;
  width: 100%;
  max-width: 382px;
  gap: 40px;
}

</style>
