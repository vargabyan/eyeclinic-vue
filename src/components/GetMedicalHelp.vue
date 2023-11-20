<script setup>
import {reactive, ref} from 'vue'
import PopupContactThePatient from "./popup/PopupContactThePatient.vue";

const responseData = [
  {
    number: '02',
    typeOfService: 'Выбрать услугу, тип проживания и транспорт',
    description: 'Nunc nunc tortor et in enim. Suspendisse eu sed commodo ac in lectus vestibulum. Habitasse tortor id volutpat eros hac.',
  },
  {
    number: '03',
    typeOfService: 'Получить расчет стоимости',
    description: 'Nunc nunc tortor et in enim. Suspendisse eu sed commodo ac in lectus vestibulum. Habitasse tortor id volutpat eros hac.',
  },
  {
    number: '04',
    typeOfService: 'Подготовка приезда',
    description: 'Nunc nunc tortor et in enim. Suspendisse eu sed commodo ac in lectus vestibulum. Habitasse tortor id volutpat eros hac.',
  },
  {
    number: '05',
    typeOfService: 'Размещение и лечение',
    description: 'Nunc nunc tortor et in enim. Suspendisse eu sed commodo ac in lectus vestibulum. Habitasse tortor id volutpat eros hac.',
  },
]

const handelPopup = reactive({popupStatus: false})
const windowWidth = ref(window.innerWidth)
const handle = ref(windowWidth.value >= 768)

window.addEventListener('resize', () => {
  windowWidth.value = window.innerWidth

  handle.value = windowWidth.value >= 768
})

const handleOpen = () => {
  handle.value = !handle.value
}

const handelButton = () => {
  handelPopup.popupStatus = !handelPopup.popupStatus
}

</script>

<template>
  <div class="get-medical-help-wrapper">
    <div class="get-medical-help container-offset">
      <h1 class="get-medical-help_header">Как получить медицицинскую помощь у нас?</h1>
      <div class="get-medical-help_content">
        <div class="get-medical-help_content_item">
          <div class="get-medical-help_item_text-wrapper">
            <div class="get-medical-help_item_number">01</div>
            <h2 class="get-medical-help_item_header">Обращение в отдел медицинского туризма</h2>
            <img class="get-medical-help_item_img" src="/src/assets/images/image%20180%202.png" alt=""
                 v-show="windowWidth <= 768">
            <button class="get-medical-help_item_button" @click="handelButton">Получить консультацию</button>
          </div>
          <img class="get-medical-help_item_img" src="/src/assets/images/image%20180.png" alt=""
               v-show="windowWidth > 768">
        </div>

        <div class="get-medical-help_content_item" v-show="handle" v-for="item in responseData">
          <div class="get-medical-help_item_text-wrapper">
            <div class="get-medical-help_item_number">{{ item.number }}</div>
            <h2 class="get-medical-help_item_header">{{ item.typeOfService }}</h2>
            <p class="get-medical-help_item_text">
              {{ item.description }}
            </p>
          </div>
        </div>

        <div class="get-medical-help_button-open-wrapper" v-show="windowWidth <= 768">
          <strong class="get-medical-help_button-open">
            Раскрыть полный список
            <span @click="handleOpen">ещё 4 шага</span>
          </strong>
        </div>

      </div>
    </div>
    <div class="download-file container-offset">
      <strong class="download-file_text">памятка пациенту<span>PDF,11 КБ</span></strong>
      <a class="download-file_button" href="">Скачать памятку</a>
    </div>
  </div>
  <PopupContactThePatient v-bind:handelPopup="handelPopup"/>
</template>

<style scoped>

.get-medical-help-wrapper {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.get-medical-help {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.get-medical-help_header {
  color: var(--Main);
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.64px;
}

.get-medical-help_content {
  display: grid;
  grid-template-areas:
        'A A   A B  B B'
        'C C   D D  E E';
  gap: 16px;
}

.get-medical-help_content_item {
  display: flex;
  padding: 30px;
  gap: 30px;
  border-radius: 10px;
  background: var(--Tretiary);
  justify-content: space-between;
}

.get-medical-help_content_item:nth-child(1) {
  grid-area: A;
  background: #F2F6F8;
  max-width: 492px;
  width: 100%;
}

.get-medical-help_content_item:nth-child(2) {
  grid-area: B;
  max-width: 492px;
  width: 100%;
}

.get-medical-help_content_item:nth-child(3) {
  grid-area: C;
}

.get-medical-help_content_item:nth-child(4) {
  grid-area: D;
}

.get-medical-help_content_item:nth-child(5) {
  grid-area: E;
}

.get-medical-help_item_text-wrapper {
  display: flex;
  flex-direction: column;
  gap: 16px;
  max-width: 303px;
}

.get-medical-help_item_number {
  width: 37px;
  height: 37px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  background: var(--Background-4);
  color: var(--Text-2);
  font-size: 14px;
  font-weight: 500;
  letter-spacing: -0.28px;
}

.get-medical-help_item_header {
  color: var(--Main);
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
  text-transform: uppercase;
  margin-top: 4px;
  max-width: 260px;
}

.get-medical-help_item_button {
  display: flex;
  padding: 18px 28px;
  border-radius: 12px;
  background: var(--Primary);
  color: var(--White);
  text-align: center;
  font-size: 14px;
  font-weight: 700;
  letter-spacing: -0.28px;
  text-transform: uppercase;
  width: max-content;
  margin-top: 39px;
}

.get-medical-help_item_img {
  max-width: 155px;
  width: 100%;
  max-height: 205px;
  border-radius: 10px;
  object-fit: cover;
}

.get-medical-help_item_text {
  color: var(--Black);
  font-size: 16px;
  line-height: 24px;
}

.download-file {
  display: flex;
  justify-content: space-between;
  gap: 30px;
  padding: 24px 42px !important;
}

.download-file_text {
  color: var(--Black);
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
  text-transform: uppercase;
  display: flex;
  align-items: center;
  gap: 6px;
}

.download-file_text:before {
  display: block;
  content: '';
  width: 50px;
  height: 50px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='50' height='51' viewBox='0 0 50 51' fill='none'%3E%3Cg clip-path='url(%23clip0_320_4263)'%3E%3Cpath d='M15.5938 0.958008H41.9609C42.6081 0.958008 43.1328 1.48267 43.1328 2.12988V42.0713C43.1328 42.7185 42.6081 43.2432 41.9609 43.2432H15.5938V0.958008Z' fill='%2384B8D9'/%3E%3Cpath d='M15.5938 0.958008H41.9609C42.6081 0.958008 43.1328 1.48267 43.1328 2.12988V42.0713C43.1328 42.7185 42.6081 43.2432 41.9609 43.2432H41.082V4.32715C41.082 3.67994 40.5574 3.15527 39.9102 3.15527H16.7656C16.1184 3.15527 15.5938 2.63061 15.5938 1.9834V0.958008Z' fill='%2355A6D9'/%3E%3Cpath d='M15.5938 0.958008L34.5391 8.72168V43.2432H15.5938V0.958008Z' fill='%23F7931D'/%3E%3Cpath d='M15.5938 3.00879L34.5391 10.7725V45.2939H15.5938V3.00879Z' fill='%23FBB03C'/%3E%3Cpath d='M7 9.84473C7 9.19752 7.52467 8.67285 8.17188 8.67285H34.5391V50.958H8.17187C7.52467 50.958 7 50.4333 7 49.7861V9.84473Z' fill='%23F2F2F2'/%3E%3Cg filter='url(%23filter0_i_320_4263)'%3E%3Cpath d='M22.034 14.2243C21.9653 14.1707 21.8806 14.1416 21.7935 14.1416C21.7063 14.1416 21.6216 14.1707 21.5529 14.2243L16.3666 18.2683C16.1403 18.4448 16.0545 18.7476 16.1547 19.0166L16.1666 19.0486C16.3159 19.4492 16.8113 19.5895 17.1485 19.3266V24.1219C17.1489 24.3272 17.2307 24.524 17.3759 24.6692C17.5211 24.8144 17.7179 24.8962 17.9232 24.8966H25.6706C25.876 24.8962 26.0728 24.8144 26.218 24.6692C26.3632 24.524 26.445 24.3272 26.4454 24.1219V19.3301C26.7826 19.593 27.278 19.4527 27.4273 19.052L27.4392 19.0201C27.5394 18.7512 27.4536 18.4483 27.2272 18.2718L22.034 14.2243Z' fill='%23FBB03C'/%3E%3C/g%3E%3Cpath d='M34.5391 8.67285H8.17188C7.52467 8.67285 7 9.19752 7 9.84473V49.7861C7 50.4333 7.52467 50.958 8.17188 50.958H9.05078V12.042C9.05078 11.3948 9.57545 10.8701 10.2227 10.8701H34.5391V8.67285Z' fill='%23F2EFDF'/%3E%3Cpath d='M14.2266 32.208C14.9834 32.208 24.6331 32.208 29.3633 32.208' stroke='%2373694D' stroke-width='1.46484' stroke-linecap='round'/%3E%3Cpath d='M17.6445 26.5439C18.0645 26.5439 23.4185 26.5439 26.043 26.5439' stroke='%23F7931D' stroke-width='1.46484' stroke-linecap='round'/%3E%3Cpath d='M14.2266 36.4072C14.5098 36.4072 18.1206 36.4072 19.8906 36.4072' stroke='%2373694D' stroke-width='1.46484' stroke-linecap='round'/%3E%3Cpath d='M23.6992 36.4072C23.9824 36.4072 27.5933 36.4072 29.3633 36.4072' stroke='%2373694D' stroke-width='1.46484' stroke-linecap='round'/%3E%3Cpath d='M14.2266 40.6064C14.3682 40.6064 16.1736 40.6064 17.0586 40.6064' stroke='%2373694D' stroke-width='1.46484' stroke-linecap='round'/%3E%3Cpath d='M20.8672 40.6064C21.292 40.6064 26.7083 40.6064 29.3633 40.6064' stroke='%2373694D' stroke-width='1.46484' stroke-linecap='round'/%3E%3Cpath d='M14.2266 44.8057C14.9834 44.8057 24.6331 44.8057 29.3633 44.8057' stroke='%2373694D' stroke-width='1.46484' stroke-linecap='round'/%3E%3C/g%3E%3Cdefs%3E%3Cfilter id='filter0_i_320_4263' x='16.1133' y='14.1416' width='11.3672' height='10.7549' filterUnits='userSpaceOnUse' color-interpolation-filters='sRGB'%3E%3CfeFlood flood-opacity='0' result='BackgroundImageFix'/%3E%3CfeBlend mode='normal' in='SourceGraphic' in2='BackgroundImageFix' result='shape'/%3E%3CfeColorMatrix in='SourceAlpha' type='matrix' values='0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0' result='hardAlpha'/%3E%3CfeOffset dy='1.66016'/%3E%3CfeComposite in2='hardAlpha' operator='arithmetic' k2='-1' k3='1'/%3E%3CfeColorMatrix type='matrix' values='0 0 0 0 0.968627 0 0 0 0 0.576471 0 0 0 0 0.113725 0 0 0 1 0'/%3E%3CfeBlend mode='normal' in2='shape' result='effect1_innerShadow_320_4263'/%3E%3C/filter%3E%3CclipPath id='clip0_320_4263'%3E%3Crect width='50' height='50' fill='white' transform='translate(0 0.958008)'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E");
  margin-right: 57px;
}

.download-file_text span {
  color: var(--Text);
}

.download-file_button {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 213px;
  height: 40px;
  border-radius: 12px;
  background: var(--Hover);
  color: var(--White);
  font-size: 14px;
  font-weight: 700;
  letter-spacing: -0.28px;
  text-transform: uppercase;
}

@media (max-width: 1200px) {

  .get-medical-help_content {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
  }
}

@media (max-width: 768px) {

  .get-medical-help_content {
    width: min-content;
  }

  .get-medical-help_header {
    font-size: 28px;
  }

  .get-medical-help_content_item:nth-child(1) .get-medical-help_item_text-wrapper {
    max-width: 100%;
  }

  .get-medical-help_item_text-wrapper {
    gap: 24px;
  }

  .get-medical-help_item_button {
    margin-top: 0;
  }

  .get-medical-help_item_img {
    max-width: 100%;
    width: 100%;
    object-position: 50% 20%;
  }

  .get-medical-help_button-open-wrapper {
    display: flex;
    justify-content: center;
    width: 100%;
  }

  .get-medical-help_button-open {
    color: var(--Black);
    text-align: center;
    font-size: 16px;
    font-weight: 700;
    line-height: 20px;
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
  }

  .get-medical-help_button-open span {
    color: var(--Text);
    display: flex;
    gap: 12px;
  }

  .get-medical-help_button-open span:after {
    display: block;
    content: '';
    width: 14px;
    height: 10px;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='14' height='11' viewBox='0 0 14 11' fill='none'%3E%3Cpath d='M7.03906 10.9766C7.17448 10.9766 7.29948 10.9505 7.41406 10.8984C7.52865 10.8463 7.63802 10.7682 7.74219 10.6641L13.6953 4.57812C13.8672 4.40625 13.9531 4.19271 13.9531 3.9375C13.9531 3.77083 13.9115 3.61719 13.8281 3.47656C13.75 3.33594 13.6432 3.22396 13.5078 3.14062C13.3724 3.0625 13.2187 3.02344 13.0469 3.02344C12.8021 3.02344 12.5833 3.11719 12.3906 3.30469L7.03906 8.78906L1.68754 3.30469C1.49484 3.11719 1.27344 3.02344 1.02344 3.02344C0.856736 3.02344 0.705736 3.0625 0.570336 3.14062C0.429636 3.22396 0.320336 3.33594 0.242236 3.47656C0.158836 3.61719 0.117236 3.77083 0.117236 3.9375C0.117236 4.19271 0.205736 4.40625 0.382836 4.57812L6.33594 10.6641C6.44011 10.7682 6.54948 10.8463 6.66406 10.8984C6.77865 10.9505 6.90365 10.9766 7.03906 10.9766Z' fill='%23132E6B'/%3E%3C/svg%3E");
  }

  .download-file {
    flex-direction: column;
    align-items: center;
    gap: 24px;
  }

  .download-file_text {
    flex-direction: column;
  }

  .download-file_text:before {
    margin-right: 0;
    margin-bottom: 24px;
  }
}

</style>
