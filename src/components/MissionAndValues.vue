<script setup>
import {ref, createApp} from 'vue'

const SpecialistAllSpecialists = {
  template: '<a class="specialist_all-specialists" href="">Все специалисты</a>'
}

const SpecialistAllSpecialists1 = {
  template: '<a class="specialist_all-specialists" href="">Все специалисты</a>'
}

createApp({
  components: {
    SpecialistAllSpecialists
  },
})
</script>

<template>
  <div class="mission-and-values-wrapper">
    <div class="mission-and-values container-offset">
      <h1 class="mission-and-values_header">Миссия и ценности центра</h1>
      <div class="mission-and-values_content-wrapper">
        <img class="mission-and-values_img" src="/src/assets/images/image%2014.png" alt="">
        <div class="mission-and-values_content">
          <h2 class="mission-and-values_name">Шиловских Олег Владимирович</h2>
          <strong class="mission-and-values_job-title">Генеральный директор</strong>
          <div class="mission-and-values_content-text">
            <div class="mission-and-values_text-wrapper">
              <p class="mission-and-values_text">Миссия центра - оказание доступной высококвалифицированной
                офтальмологической помощи от консультаций до
                сложнейших микрохирургических операций.</p>
              <p class="mission-and-values_text">Уникальность Центра - в высокой надежности лечения и постоянном
                совершенствовании диагностических и
                хирургических технологий.</p>
              <p class="mission-and-values_text">Коллектив клиники – сильная и сплоченная команда, всем сердцем
                преданная своему любимому делу. Это
                профессионалы высокой квалификации, объединенные общей целью – возвращать зрение тысячам людей – и
                стремлением достичь успеха, быть лучшими в своей сфере.</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="mission-and-values-footer">
      <div class="our-team container-offset">
        <h1 class="our-team_header">Наша команда</h1>
        <div class="our-team_item-wrapper">
          <div class="our-team_item">
            <p class="our-team_count">92</p>
            <strong class="our-team_specialist">
              специалиста высшей категории
            </strong>
          </div>
          <div class="our-team_item">
            <p class="our-team_count">2</p>
            <strong class="our-team_specialist">
              доктора медицинских наук
            </strong>
          </div>
          <div class="our-team_item">
            <p class="our-team_count">12</p>
            <strong class="our-team_specialist">
              кандидатов медицинских наук
            </strong>
          </div>

          <specialist-all-specialists/>
          <SpecialistAllSpecialists/>

        </div>
      </div>

      <div class="specialist container-offset">
        <div class="specialist_content">
          <img class="specialist_img" src="/src/assets/images/image%2017.png" alt="">
          <div class="specialist_text-wrapper">
            <strong class="specialist_job-title">Офтальмолог</strong>
            <p class="specialist_profession">
              <span class="specialist_name">Зиблат Екатерина Максимовна</span>
              Врач-офтальмолог, отделения по клинико- экспертной работе, образование высшее, имеет высшую
              квалификационную
              категорию.
            </p>
          </div>
        </div>
        <!--        { specialistAllSpecialists }-->
      </div>
    </div>
  </div>
</template>

<style scoped>

.mission-and-values-wrapper {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.mission-and-values {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.mission-and-values_header {
  color: var(--Main);
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.64px;
}

.mission-and-values_content-wrapper {
  display: flex;
  gap: 40px;
  justify-content: space-between;
}

.mission-and-values_img {
  max-width: 350px;
  width: 100%;
  max-height: 372px;
  border-radius: 10px;
}

.mission-and-values_content {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.mission-and-values_name {
  color: var(--Black);
  font-size: 20px;
  font-weight: 700;
  line-height: 16px;
  text-transform: uppercase;
}

.mission-and-values_job-title {
  color: var(--Primary);
  font-size: 14px;
  font-weight: 700;
  letter-spacing: -0.28px;
  text-transform: uppercase;
}

.mission-and-values_content-text {
  display: flex;
  padding: 30px 16px;
  gap: 16px;
}

.mission-and-values_content-text:before {
  display: block;
  content: '';
  width: 85px;
  height: 27px;
  background-image: url("data:image/svg+xml,%3Csvg width='27' height='27' viewBox='0 0 27 27' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cg clip-path='url(%23clip0_320_1848)'%3E%3Cpath d='M0.00574056 18.7357C0.00574056 22.2854 2.88322 25.1629 6.43294 25.1629C9.9827 25.1629 12.8602 22.2854 12.8602 18.7357C12.8602 15.1859 9.9827 12.3085 6.43294 12.3085C5.70342 12.3085 5.00509 12.4356 4.35135 12.6598C5.79775 4.3643 12.2666 -0.985332 6.26999 3.41752C-0.379348 8.29979 -0.00138087 18.5392 0.00605943 18.7269C0.00605943 18.7298 0.00574056 18.7324 0.00574056 18.7357Z' fill='%239FAEB6'/%3E%3Cpath d='M14.1464 18.7357C14.1464 22.2854 17.0239 25.1629 20.5736 25.1629C24.1234 25.1629 27.0009 22.2854 27.0009 18.7357C27.0009 15.1859 24.1233 12.3085 20.5736 12.3085C19.844 12.3085 19.1457 12.4356 18.492 12.6598C19.9384 4.3643 26.4073 -0.985332 20.4106 3.41752C13.7613 8.29979 14.1392 18.5392 14.1467 18.7269C14.1467 18.7298 14.1464 18.7324 14.1464 18.7357Z' fill='%239FAEB6'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0_320_1848'%3E%3Crect width='27' height='27' fill='white'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E%0A");
}

.mission-and-values_text-wrapper {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.mission-and-values_text {
  color: var(--Text-2);
  font-size: 16px;
}

.mission-and-values-footer {
  display: flex;
  gap: 20px;
}

.our-team {
  display: flex;
  flex-direction: column;
  gap: 24px;
  max-width: 519px;
  width: 100%;
}

.our-team_header {
  color: var(--Main);
  font-size: 26px;
  font-weight: 700;
  letter-spacing: -0.52px;
}

.our-team_item-wrapper {
  display: grid;
  grid-template-columns: auto auto auto;
  gap: 16px;
}

.our-team_item {
  display: flex;
  padding: 16px 16px 22px 16px;
  flex-direction: column;
  gap: 10px;
  border-radius: 10px;
  background: var(--Tretiary);
}

.our-team_count {
  color: var(--Main);
  font-size: 36px;
  font-weight: 700;
  letter-spacing: -0.72px;
}

.our-team_specialist {
  color: var(--Main);
  font-size: 12px;
  font-weight: 700;
  line-height: 16px;
  text-transform: uppercase;
}

.specialist {
  display: flex;
  flex-direction: column;
  gap: 30px;
  max-width: 502px;
}

.specialist_content {
  display: flex;
  gap: 18px;
}

.specialist_img {
  max-width: 143px;
  width: 100%;
  max-height: 141px;
  border-radius: 10px;
}

.specialist_text-wrapper {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.specialist_job-title {
  color: var(--Primary);
  font-size: 14px;
  font-weight: 700;
  letter-spacing: -0.28px;
  text-transform: uppercase;
}

.specialist_profession {
  color: var(--Black);
  font-size: 14px;
  letter-spacing: -0.28px;
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.specialist_name {
  color: var(--Black);
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
}

.specialist_all-specialists {
  color: var(--Main);
  font-size: 16px;
  font-weight: 500;
  display: flex;
  gap: 12px;
  align-items: center;
}

.specialist_all-specialists:before {
  display: block;
  content: '';
  width: 30px;
  height: 15px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='30' height='15' viewBox='0 0 30 15' fill='none'%3E%3Cpath d='M9.82031 14.5235H19.6328C20.2526 14.5235 20.6849 14.4349 20.9297 14.2578C21.1797 14.086 21.3047 13.8282 21.3047 13.4844C21.3047 12.9844 21.151 12.4558 20.8437 11.8985C20.5417 11.3412 20.1042 10.8203 19.5312 10.336C18.9635 9.84636 18.2734 9.45052 17.4609 9.14843C16.6536 8.84114 15.7422 8.6875 14.7265 8.6875C13.7161 8.6875 12.8047 8.84114 11.9922 9.14843C11.1849 9.45052 10.4948 9.84636 9.92191 10.336C9.34896 10.8203 8.91146 11.3412 8.60937 11.8985C8.30729 12.4558 8.15625 12.9844 8.15625 13.4844C8.15625 13.8282 8.27864 14.086 8.52343 14.2578C8.77343 14.4349 9.20573 14.5235 9.82031 14.5235ZM14.7344 7.28906C15.2917 7.28906 15.8073 7.13802 16.2812 6.83593C16.7552 6.52864 17.1354 6.11458 17.4219 5.59375C17.7135 5.07291 17.8594 4.48698 17.8594 3.83593C17.8594 3.19531 17.7135 2.62239 17.4219 2.11718C17.1354 1.60677 16.7552 1.20573 16.2812 0.914064C15.8073 0.622397 15.2917 0.476562 14.7344 0.476562C14.1771 0.476562 13.6614 0.625001 13.1875 0.921874C12.7135 1.21875 12.3307 1.62239 12.039 2.13281C11.7526 2.64323 11.6094 3.21614 11.6094 3.85156C11.6094 4.49739 11.7526 5.08073 12.039 5.60156C12.3307 6.11718 12.7135 6.52864 13.1875 6.83593C13.6614 7.13802 14.1771 7.28906 14.7344 7.28906ZM1.375 14.5235H7.30468C7.10156 14.2266 7.00521 13.8698 7.01562 13.4532C7.02604 13.0365 7.12239 12.599 7.30468 12.1407C7.48698 11.6823 7.73698 11.2396 8.05468 10.8125C8.3776 10.3802 8.75 9.99996 9.17187 9.67187C8.73437 9.38021 8.23177 9.14062 7.66406 8.95312C7.10156 8.76041 6.45573 8.66406 5.72656 8.66406C4.84635 8.66406 4.05208 8.80989 3.34375 9.10156C2.64062 9.38802 2.03906 9.76826 1.53906 10.2422C1.04427 10.711 0.664063 11.224 0.398438 11.7813C0.132813 12.3386 0 12.8881 0 13.4297C0 13.7787 0.104167 14.0469 0.3125 14.2344C0.526042 14.4271 0.880208 14.5235 1.375 14.5235ZM5.72656 7.46875C6.21614 7.46875 6.66666 7.33593 7.07812 7.07031C7.48958 6.80468 7.82031 6.44531 8.07031 5.99218C8.32031 5.53385 8.44531 5.02343 8.44531 4.46093C8.44531 3.89843 8.32031 3.39843 8.07031 2.96093C7.82031 2.51823 7.48698 2.17187 7.07031 1.92187C6.65885 1.66666 6.21093 1.53906 5.72656 1.53906C5.24739 1.53906 4.79948 1.66927 4.38281 1.92968C3.97135 2.18489 3.63802 2.53385 3.38281 2.97656C3.1276 3.41927 3.0026 3.91927 3.00781 4.47656C3.00781 5.03385 3.13281 5.53906 3.38281 5.99218C3.63281 6.44531 3.96354 6.80468 4.375 7.07031C4.79166 7.33593 5.24218 7.46875 5.72656 7.46875ZM28.0781 14.5235C28.5729 14.5235 28.9245 14.4271 29.1328 14.2344C29.3463 14.0469 29.4531 13.7787 29.4531 13.4297C29.4531 12.8881 29.3203 12.3386 29.0547 11.7813C28.7943 11.224 28.414 10.711 27.914 10.2422C27.414 9.76826 26.8099 9.38802 26.1015 9.10156C25.3984 8.80989 24.6068 8.66406 23.7265 8.66406C22.9974 8.66406 22.3489 8.76041 21.7812 8.95312C21.2187 9.14062 20.7187 9.38021 20.2812 9.67187C20.7031 9.99996 21.0729 10.3802 21.3906 10.8125C21.7135 11.2396 21.9661 11.6823 22.1484 12.1407C22.3307 12.599 22.4271 13.0365 22.4375 13.4532C22.4479 13.8698 22.3515 14.2266 22.1484 14.5235H28.0781ZM23.7265 7.46875C24.2109 7.46875 24.6588 7.33593 25.0703 7.07031C25.487 6.80468 25.8203 6.44531 26.0703 5.99218C26.3203 5.53906 26.4453 5.03385 26.4453 4.47656C26.4453 3.91927 26.3177 3.41927 26.0625 2.97656C25.8125 2.53385 25.4792 2.18489 25.0625 1.92968C24.651 1.66927 24.2057 1.53906 23.7265 1.53906C23.2422 1.53906 22.7917 1.66666 22.375 1.92187C21.9635 2.17187 21.6328 2.51823 21.3828 2.96093C21.1328 3.39843 21.0078 3.89843 21.0078 4.46093C21.0078 5.02343 21.1328 5.53385 21.3828 5.99218C21.6328 6.44531 21.9635 6.80468 22.375 7.07031C22.7864 7.33593 23.237 7.46875 23.7265 7.46875Z' fill='%23FF8D76'/%3E%3C/svg%3E");
}

.specialist_all-specialists:after {
  display: block;
  content: '';
  width: 8px;
  height: 14px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='9' height='15' viewBox='0 0 9 15' fill='none'%3E%3Cpath d='M8.40625 7.4961C8.40625 7.36068 8.38021 7.23568 8.32813 7.1211C8.27604 7.00651 8.19792 6.89714 8.09375 6.79297L2.00781 0.839844C1.83594 0.667969 1.6224 0.582031 1.36719 0.582031C1.20052 0.582031 1.04688 0.623698 0.906249 0.707031C0.765625 0.785157 0.653646 0.891927 0.570312 1.02734C0.492188 1.16276 0.453125 1.31641 0.453125 1.48828C0.453125 1.73307 0.546876 1.95182 0.734376 2.14453L6.21875 7.4961L0.734376 12.8476C0.546876 13.0403 0.453125 13.2617 0.453125 13.5117C0.453125 13.6784 0.492188 13.8294 0.570312 13.9648C0.653646 14.1055 0.765625 14.2148 0.906249 14.2929C1.04688 14.3763 1.20052 14.4179 1.36719 14.4179C1.6224 14.4179 1.83594 14.3294 2.00781 14.1523L8.09375 8.19922C8.19792 8.09505 8.27604 7.98568 8.32813 7.8711C8.38021 7.75651 8.40625 7.63151 8.40625 7.4961Z' fill='%23132E6B'/%3E%3C/svg%3E");
}

@media (max-width: 768px) {

  .mission-and-values {
    display: none !important;
  }

  .mission-and-values-footer {
    flex-direction: column;
    gap: 20px;
  }

  .our-team {
    max-width: fit-content;
  }

  .our-team_header {
    color: var(--Main);
    font-size: 26px;
    font-weight: 700;
    letter-spacing: -0.52px;
  }

  .our-team_item-wrapper {
    gap: 16px;
    width: 100%;
    display: grid;
    grid-template-areas:
            'A B'
            'C C';
  }

  .our-team_item {
    display: flex;
    padding: 16px 16px 22px 16px;
    flex-direction: column;
    gap: 10px;
    border-radius: 10px;
    background: var(--Tretiary);
  }

  .our-team_item:nth-child(1) {
    grid-area: A;
  }

  .our-team_item:nth-child(2) {
    grid-area: B;
  }

  .our-team_item:nth-child(3) {
    grid-area: C;
  }

  .our-team_item:nth-child(3) .our-team_count {
    display: none;
  }

  .our-team_count {
    color: var(--Main);
    font-size: 36px;
    font-weight: 700;
    letter-spacing: -0.72px;
  }

  .our-team_specialist {
    color: var(--Main);
    font-size: 12px;
    font-weight: 700;
    line-height: 16px;
    text-transform: uppercase;
  }

  .specialist {
    display: flex;
    flex-direction: column;
    gap: 30px;
    max-width: 502px;
  }

  .specialist_content {
    display: flex;
    gap: 18px;
  }

  .specialist_img {
    max-width: 143px;
    width: 100%;
    max-height: 141px;
    border-radius: 10px;
  }

  .specialist_text-wrapper {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .specialist_job-title {
    color: var(--Primary);
    font-size: 14px;
    font-weight: 700;
    letter-spacing: -0.28px;
    text-transform: uppercase;
  }

  .specialist_profession {
    color: var(--Black);
    font-size: 14px;
    letter-spacing: -0.28px;
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .specialist_name {
    color: var(--Black);
    font-size: 16px;
    font-weight: 700;
    line-height: 20px;
  }

  .specialist_all-specialists {
    color: var(--Main);
    font-size: 16px;
    font-weight: 500;
    display: flex;
    gap: 12px;
    align-items: center;
  }

  .specialist_all-specialists:before {
    display: block;
    content: '';
    width: 30px;
    height: 15px;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='30' height='15' viewBox='0 0 30 15' fill='none'%3E%3Cpath d='M9.82031 14.5235H19.6328C20.2526 14.5235 20.6849 14.4349 20.9297 14.2578C21.1797 14.086 21.3047 13.8282 21.3047 13.4844C21.3047 12.9844 21.151 12.4558 20.8437 11.8985C20.5417 11.3412 20.1042 10.8203 19.5312 10.336C18.9635 9.84636 18.2734 9.45052 17.4609 9.14843C16.6536 8.84114 15.7422 8.6875 14.7265 8.6875C13.7161 8.6875 12.8047 8.84114 11.9922 9.14843C11.1849 9.45052 10.4948 9.84636 9.92191 10.336C9.34896 10.8203 8.91146 11.3412 8.60937 11.8985C8.30729 12.4558 8.15625 12.9844 8.15625 13.4844C8.15625 13.8282 8.27864 14.086 8.52343 14.2578C8.77343 14.4349 9.20573 14.5235 9.82031 14.5235ZM14.7344 7.28906C15.2917 7.28906 15.8073 7.13802 16.2812 6.83593C16.7552 6.52864 17.1354 6.11458 17.4219 5.59375C17.7135 5.07291 17.8594 4.48698 17.8594 3.83593C17.8594 3.19531 17.7135 2.62239 17.4219 2.11718C17.1354 1.60677 16.7552 1.20573 16.2812 0.914064C15.8073 0.622397 15.2917 0.476562 14.7344 0.476562C14.1771 0.476562 13.6614 0.625001 13.1875 0.921874C12.7135 1.21875 12.3307 1.62239 12.039 2.13281C11.7526 2.64323 11.6094 3.21614 11.6094 3.85156C11.6094 4.49739 11.7526 5.08073 12.039 5.60156C12.3307 6.11718 12.7135 6.52864 13.1875 6.83593C13.6614 7.13802 14.1771 7.28906 14.7344 7.28906ZM1.375 14.5235H7.30468C7.10156 14.2266 7.00521 13.8698 7.01562 13.4532C7.02604 13.0365 7.12239 12.599 7.30468 12.1407C7.48698 11.6823 7.73698 11.2396 8.05468 10.8125C8.3776 10.3802 8.75 9.99996 9.17187 9.67187C8.73437 9.38021 8.23177 9.14062 7.66406 8.95312C7.10156 8.76041 6.45573 8.66406 5.72656 8.66406C4.84635 8.66406 4.05208 8.80989 3.34375 9.10156C2.64062 9.38802 2.03906 9.76826 1.53906 10.2422C1.04427 10.711 0.664063 11.224 0.398438 11.7813C0.132813 12.3386 0 12.8881 0 13.4297C0 13.7787 0.104167 14.0469 0.3125 14.2344C0.526042 14.4271 0.880208 14.5235 1.375 14.5235ZM5.72656 7.46875C6.21614 7.46875 6.66666 7.33593 7.07812 7.07031C7.48958 6.80468 7.82031 6.44531 8.07031 5.99218C8.32031 5.53385 8.44531 5.02343 8.44531 4.46093C8.44531 3.89843 8.32031 3.39843 8.07031 2.96093C7.82031 2.51823 7.48698 2.17187 7.07031 1.92187C6.65885 1.66666 6.21093 1.53906 5.72656 1.53906C5.24739 1.53906 4.79948 1.66927 4.38281 1.92968C3.97135 2.18489 3.63802 2.53385 3.38281 2.97656C3.1276 3.41927 3.0026 3.91927 3.00781 4.47656C3.00781 5.03385 3.13281 5.53906 3.38281 5.99218C3.63281 6.44531 3.96354 6.80468 4.375 7.07031C4.79166 7.33593 5.24218 7.46875 5.72656 7.46875ZM28.0781 14.5235C28.5729 14.5235 28.9245 14.4271 29.1328 14.2344C29.3463 14.0469 29.4531 13.7787 29.4531 13.4297C29.4531 12.8881 29.3203 12.3386 29.0547 11.7813C28.7943 11.224 28.414 10.711 27.914 10.2422C27.414 9.76826 26.8099 9.38802 26.1015 9.10156C25.3984 8.80989 24.6068 8.66406 23.7265 8.66406C22.9974 8.66406 22.3489 8.76041 21.7812 8.95312C21.2187 9.14062 20.7187 9.38021 20.2812 9.67187C20.7031 9.99996 21.0729 10.3802 21.3906 10.8125C21.7135 11.2396 21.9661 11.6823 22.1484 12.1407C22.3307 12.599 22.4271 13.0365 22.4375 13.4532C22.4479 13.8698 22.3515 14.2266 22.1484 14.5235H28.0781ZM23.7265 7.46875C24.2109 7.46875 24.6588 7.33593 25.0703 7.07031C25.487 6.80468 25.8203 6.44531 26.0703 5.99218C26.3203 5.53906 26.4453 5.03385 26.4453 4.47656C26.4453 3.91927 26.3177 3.41927 26.0625 2.97656C25.8125 2.53385 25.4792 2.18489 25.0625 1.92968C24.651 1.66927 24.2057 1.53906 23.7265 1.53906C23.2422 1.53906 22.7917 1.66666 22.375 1.92187C21.9635 2.17187 21.6328 2.51823 21.3828 2.96093C21.1328 3.39843 21.0078 3.89843 21.0078 4.46093C21.0078 5.02343 21.1328 5.53385 21.3828 5.99218C21.6328 6.44531 21.9635 6.80468 22.375 7.07031C22.7864 7.33593 23.237 7.46875 23.7265 7.46875Z' fill='%23FF8D76'/%3E%3C/svg%3E");
  }

  .specialist_all-specialists:after {
    display: block;
    content: '';
    width: 8px;
    height: 14px;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='9' height='15' viewBox='0 0 9 15' fill='none'%3E%3Cpath d='M8.40625 7.4961C8.40625 7.36068 8.38021 7.23568 8.32813 7.1211C8.27604 7.00651 8.19792 6.89714 8.09375 6.79297L2.00781 0.839844C1.83594 0.667969 1.6224 0.582031 1.36719 0.582031C1.20052 0.582031 1.04688 0.623698 0.906249 0.707031C0.765625 0.785157 0.653646 0.891927 0.570312 1.02734C0.492188 1.16276 0.453125 1.31641 0.453125 1.48828C0.453125 1.73307 0.546876 1.95182 0.734376 2.14453L6.21875 7.4961L0.734376 12.8476C0.546876 13.0403 0.453125 13.2617 0.453125 13.5117C0.453125 13.6784 0.492188 13.8294 0.570312 13.9648C0.653646 14.1055 0.765625 14.2148 0.906249 14.2929C1.04688 14.3763 1.20052 14.4179 1.36719 14.4179C1.6224 14.4179 1.83594 14.3294 2.00781 14.1523L8.09375 8.19922C8.19792 8.09505 8.27604 7.98568 8.32813 7.8711C8.38021 7.75651 8.40625 7.63151 8.40625 7.4961Z' fill='%23132E6B'/%3E%3C/svg%3E");
  }

}

</style>
