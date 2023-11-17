<script setup>

</script>

<template>
  <div class="local-ethics-committee">
    <h1 class="local-ethics-committee_header">Локальный этический комитет</h1>
    <div class="local-ethics-committee_items-wrapper">

      <div class="local-ethics-committee_item" v-for="item in 8">
        <div class="local-ethics-committee_item_svg"></div>
        <div class="local-ethics-committee_item_content">
          <strong class="local-ethics-committee_item_name">Положение об этическом комитете</strong>
          <div class="local-ethics-committee_item_doc-wrapper">
            <p class="local-ethics-committee_item_type-doc">DOCX,11 КБ</p>
            <a class="local-ethics-committee_item_download" href="">Скачать</a>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<style scoped>

.local-ethics-committee {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.local-ethics-committee_header {
  color: var(--Primary);
  font-size: 40px;
  font-weight: 700;
  letter-spacing: -0.8px;
}

.local-ethics-committee_items-wrapper {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}

.local-ethics-committee_item {
  display: flex;
  max-width: 340px;
  width: 100%;
  padding: 22px;
  gap: 16px;
  border-radius: 10px;
  background: #FFF;
}

.local-ethics-committee_item_svg {
  display: block;
  content: '';
  max-width: 45px;
  width: 100%;
  height: 50px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='47' height='50' viewBox='0 0 47 50' fill='none'%3E%3Cpath d='M39.0625 50H7.8125C5.21875 50 3.125 47.9062 3.125 45.3125V4.6875C3.125 2.09375 5.21875 0 7.8125 0H29.9688C31.2188 0 32.4062 0.5 33.2812 1.375L42.375 10.4688C43.25 11.3438 43.75 12.5312 43.75 13.7812V45.3125C43.75 47.9062 41.6562 50 39.0625 50ZM7.8125 3.125C6.9375 3.125 6.25 3.8125 6.25 4.6875V45.3125C6.25 46.1875 6.9375 46.875 7.8125 46.875H39.0625C39.9375 46.875 40.625 46.1875 40.625 45.3125V13.7812C40.6275 13.5763 40.5871 13.3731 40.5064 13.1848C40.4256 12.9964 40.3064 12.827 40.1562 12.6875L31.0625 3.59375C30.7721 3.30215 30.3802 3.13418 29.9688 3.125H7.8125Z' fill='%23DEE8EE'/%3E%3Cpath d='M41.8125 15.6255H32.7188C30.1875 15.6255 28.125 13.563 28.125 11.0317V1.93799C28.125 1.06299 28.8125 0.375488 29.6875 0.375488C30.5625 0.375488 31.25 1.06299 31.25 1.93799V11.0317C31.25 11.8442 31.9062 12.5005 32.7188 12.5005H41.8125C42.6875 12.5005 43.375 13.188 43.375 14.063C43.375 14.938 42.6875 15.6255 41.8125 15.6255ZM31.25 40.6255H15.625C14.75 40.6255 14.0625 39.938 14.0625 39.063C14.0625 38.188 14.75 37.5005 15.625 37.5005H31.25C32.125 37.5005 32.8125 38.188 32.8125 39.063C32.8125 39.938 32.125 40.6255 31.25 40.6255ZM31.25 31.2505H15.625C14.75 31.2505 14.0625 30.563 14.0625 29.688C14.0625 28.813 14.75 28.1255 15.625 28.1255H31.25C32.125 28.1255 32.8125 28.813 32.8125 29.688C32.8125 30.563 32.125 31.2505 31.25 31.2505ZM21.875 21.8755H15.625C14.75 21.8755 14.0625 21.188 14.0625 20.313C14.0625 19.438 14.75 18.7505 15.625 18.7505H21.875C22.75 18.7505 23.4375 19.438 23.4375 20.313C23.4375 21.188 22.75 21.8755 21.875 21.8755Z' fill='%23DEE8EE'/%3E%3C/svg%3E");
}

.local-ethics-committee_item_content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 6px;
  width: 100%;
}

.local-ethics-committee_item_doc-wrapper {
  display: flex;
  justify-content: space-between;
}

.local-ethics-committee_item_name {
  color: var(--Main);
  font-size: 14px;
  font-weight: 500;
  letter-spacing: -0.28px;
  text-decoration-line: underline;
}

.local-ethics-committee_item_type-doc {
  color: var(--Text);
  font-size: 12px;
  font-weight: 500;
  letter-spacing: -0.24px;
  text-decoration-line: underline;
}

.local-ethics-committee_item_download {
  color: var(--Primary);
  font-size: 12px;
  font-weight: 700;
  line-height: 20px;
  text-decoration-line: underline;
  text-transform: uppercase;
}

@media (max-width: 768px) {

  .local-ethics-committee {
    gap: 20px;
    padding: 40px 32px;
  }

  .local-ethics-committee_header {
    color: var(--Black);
    font-size: 26px;
    letter-spacing: -0.52px;
  }

  .local-ethics-committee_item_svg {
    max-width: 47px;
    height: 50px;
  }
}

@media (max-width: 540px) {

  .local-ethics-committee_header {
    max-width: 325px;
  }
}


</style>
