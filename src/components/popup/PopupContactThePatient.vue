<script setup>
import {reactive, ref} from 'vue'
import WrapperPopup from "./WrapperPopup.vue";
import {string} from "yup";

const buttonSubmitStatus = ref(true)
const inputStatus = reactive({
  name: {
    error: false,
    success: false,
  },
  phone: {
    error: false,
    success: false,
  },
})
const inputValues = reactive({
  name: '',
  phone: '',
  message: '',
})

const onFinish = async (e) => {
  e.preventDefault()

  const values = {
    name: await inputValues.name,
    phone: await inputValues.phone,
    message: await inputValues.message,
  }

  console.log(values)
  await fetch('/url', {
    method: 'POST',
    body: values,
    headers: {
      'Content-Type': 'text/plain;charset=UTF-8'
    },
  })
}
const checkButtonStatus = () => {
  if (inputValues.name !== '' && inputValues.phone !== '' && !inputStatus.name.error && !inputStatus.phone.error) {
    buttonSubmitStatus.value = false
  } else {
    buttonSubmitStatus.value = true
  }
}

const onChangeName = async (e) => {
  const {value} = e.target;
  const schema = string().required()

  if (await schema.matches(/^[a-zA-Z]+ [a-zA-Z]+$/).isValid(value)) {
    inputStatus.name.success = true
    inputStatus.name.error = false
  } else {
    inputStatus.name.error = true
    inputStatus.name.success = false
  }
  inputValues.name = value
  checkButtonStatus()
}

const onChangePhone = async (e) => {
  const {value} = e.target;
  const schema = string().required()

  if (await schema.matches(/^[\\+]?[(]?[0-9]{3}[)]?[-\s\\.]?[0-9]{3}[-\s\\.]?[0-9]{4,6}$/).isValid(value)) {
    inputStatus.phone.success = true
    inputStatus.phone.error = false
  } else {
    inputStatus.phone.error = true
    inputStatus.phone.success = false
  }
  inputValues.phone = value
  checkButtonStatus()
}

const onChangeMessage = async (e) => {
  const {value} = e.target;

  inputValues.message = value
}
</script>

<template>
  <WrapperPopup>
    <div class="contact-the-patient">
      <div class="contact-the-patient_header-wrapper">
        <h1 class="contact-the-patient_header">
          Заполните форму
          <span>и мы свяжемся с пациентом</span>
        </h1>
        <p class="contact-the-patient_subtitle">в течении 30 минут в рабочее время</p>
      </div>

      <form action="" class="contact-the-patient_form" @submit="onFinish">
        <div class="contact-the-patient_form_items-wrapper">
          <label class="contact-the-patient_form_item-label"
                 :class="{'contact-the-patient_form_item-label-successful': inputStatus.name.success}">
            <label class="contact-the-patient_form_description-label" v-show="inputValues.name">Как вас зовут?</label>
            <input class="contact-the-patient_form_item"
                   :class="{'contact-the-patient_form_item-successful': inputStatus.name.success, 'contact-the-patient_form_item-unsuccessful': inputStatus.name.error, 'contact-the-patient_form_item-active': inputValues.name}"
                   @change="onChangeName"
                   placeholder="ФИО контактного лица">
            {{ inputStatus.name.error ? 'Текст ошибки' : '' }}
          </label>
          <label class="contact-the-patient_form_item-label"
                 :class="{'contact-the-patient_form_item-label-successful': inputStatus.phone.success}">
            <label class="contact-the-patient_form_description-label" v-show="inputValues.phone">номер?</label>
            <input class="contact-the-patient_form_item" placeholder="Номер телефона"
                   :class="{'contact-the-patient_form_item-successful': inputStatus.phone.success, 'contact-the-patient_form_item-unsuccessful': inputStatus.phone.error, 'contact-the-patient_form_item-active': inputValues.phone}"
                   @change="onChangePhone">
            {{ inputStatus.phone.error ? 'Текст ошибки' : '' }}
          </label>
          <label class="contact-the-patient_form_item-label">
            <textarea name="message" class="contact-the-patient_form_item" placeholder="Сообщение (не обязательно)"
                      @click="onChangeMessage"/>
          </label>
        </div>
        <div class="contact-the-patient_form_button-wrapper">
          <label>
            <input class="contact-the-patient_form_button" type="submit" value="Жду звонка!"
                   :class="{'contact-the-patient_form_button-disabled': buttonSubmitStatus}"
                   :disabled="buttonSubmitStatus">
          </label>
          <p class="contact-the-patient_form_policy">
            Нажимая на кнопку , я соглашаюсь
            <span>с политикой обработки персональных данных</span>
          </p>
        </div>
      </form>
    </div>
  </WrapperPopup>
</template>

<style scoped>

.contact-the-patient {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.contact-the-patient_header-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
}

.contact-the-patient_header {
  color: #2583CE;
  text-align: center;
  font-size: 26px;
  font-weight: 700;
  letter-spacing: -0.52px;
  display: flex;
  flex-direction: column;
}

.contact-the-patient_header span {
  color: #132E6B;
}

.contact-the-patient_subtitle {
  color: var(--Text-2);
  text-align: center;
  font-size: 14px;
  letter-spacing: -0.28px;
}

.contact-the-patient_form_items-wrapper {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.contact-the-patient_form_item-label {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 8px;
  width: 100%;
  color: var(--Error);
  font-size: 14px;
  letter-spacing: -0.28px;
}

.contact-the-patient_form_item-label-successful:after {
  top: 13px;
  right: 16px;
  position: absolute;
  display: block;
  content: '';
  width: 24px;
  height: 24px;
  background-image: url("data:image/svg+xml,%3Csvg width='24' height='24' viewBox='0 0 24 24' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M6.43762 12.6425C6.1635 12.4176 5.80629 12.2955 5.43766 12.3009C5.06903 12.3062 4.71625 12.4385 4.45007 12.6712C4.18389 12.9039 4.02401 13.2199 4.00249 13.5556C3.98098 13.8914 4.09942 14.2222 4.33407 14.4816L7.57705 17.5868C7.71283 17.7168 7.87598 17.8204 8.05672 17.8913C8.23745 17.9623 8.43205 17.9993 8.62883 18C8.82456 18.001 9.01853 17.9662 9.19921 17.8975C9.37989 17.8288 9.54359 17.7277 9.68061 17.6002L19.5849 8.27119C19.7191 8.14518 19.8249 7.99628 19.8961 7.83298C19.9673 7.66968 20.0026 7.49518 19.9999 7.31945C19.9971 7.14372 19.9565 6.9702 19.8803 6.80879C19.8041 6.64738 19.6938 6.50125 19.5556 6.37874C19.4175 6.25624 19.2543 6.15974 19.0753 6.09478C18.8963 6.02982 18.705 5.99766 18.5124 6.00013C18.3198 6.00261 18.1296 6.03967 17.9527 6.10921C17.7758 6.17874 17.6156 6.27939 17.4813 6.4054L8.64344 14.7482L6.43762 12.6425Z' fill='%2327AE60'/%3E%3C/svg%3E%0A");
}

.contact-the-patient_form_description-label {
  top: 8px;
  left: 16px;
  position: absolute;
  color: var(--Text);
  font-size: 12px;
  font-weight: 500;
  letter-spacing: -0.24px;
}

.contact-the-patient_form_item {
  display: flex;
  max-width: 350px;
  width: initial;
  padding: 15px 16px 15px 16px;
  align-items: flex-start;
  gap: 10px;
  border-radius: 10px;
  background: var(--Tretiary);
  border: none;
  color: var(--Main);
  font-size: 16px;
  font-weight: 500;
}

.contact-the-patient_form_item-active {
  padding: 24px 16px 6px 16px;
  width: initial;
}

textarea.contact-the-patient_form_item {
  width: initial !important;
  height: 90px !important;
  resize: none;
}

.contact-the-patient_form_item-successful {
  background: var(--Green);
}

.contact-the-patient_form_item-unsuccessful {
  background: var(--Error-Light);
}

.contact-the-patient_form_item:hover {
  box-shadow: 3px 3px 20px 0 rgba(90, 169, 213, 0.15);
}

.contact-the-patient_form_item::placeholder {
  color: var(--Text);
  display: block !important;
}

.contact-the-patient_form {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.contact-the-patient_form_button-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 14px;
}

.contact-the-patient_form_button {
  width: 230px;
  height: 50px;
  border-radius: 12px;
  background: var(--Primary);
  color: var(--White, #FFF);
  text-align: center;
  font-size: 14px;
  font-weight: 700;
  letter-spacing: -0.28px;
  text-transform: uppercase;
  border: none;
  cursor: pointer;
}

.contact-the-patient_form_button-disabled {
  background: rgb(90 169 212 / 42%);
}

.contact-the-patient_form_policy {
  color: var(--Text);
  text-align: center;
  font-size: 14px;
  letter-spacing: -0.28px;
  display: flex;
  flex-direction: column;
}

.contact-the-patient_form_policy span {
  color: var(--Primary);
}

</style>
