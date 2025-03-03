<script setup lang="ts">
import { ref } from 'vue'

interface QRStates {
  shorts: boolean
  tat: boolean
}

const qrStates = ref<QRStates>({
  shorts: false,
  tat: false,
})

function toggleQR(project: keyof QRStates) {
  qrStates.value[project] = !qrStates.value[project]
}
</script>

<template>
  <div class="npc-paragraph">
    <section class="card">
      <h2>TAT - 北科生活</h2>
      <div class="project-content">
        <img
          class="project-image"
          src="assets/img/tat_qr_code.svg"
          @click="toggleQR('tat')"
        >
        <div class="project-description">
          <p>方便，簡潔，快速，強大，豐富您的北科生活！</p>
          <p>迅速查詢北科學生課表與行事曆，查看北科 i 學園公告，下載北科 i 學園檔案</p>
          <p>查閱北科學生成績與學分資訊，並主動推播重要消息</p>
          <p>支援中文、英文顯示，老師亦可使用</p>
          <p>即刻安裝，北科生活無煩惱～</p>
          <p>歡迎您提供寶貴的意見、錯誤回報、創意點子給我們。你的想法，我們實現！</p>
        </div>
      </div>
      <div class="download-badge">
        <a href="https://to.ntut.club/tat/ios">
          <img
            alt="Download on the App Store"
            src="assets/img/app_store.svg"
          >
        </a>
        <a href="https://to.ntut.club/tat/android">
          <img
            alt="Get it on Google Play"
            src="assets/img/google_play.svg"
          >
        </a>
      </div>
    </section>

    <section class="card">
      <h2>Shorts - 短褲</h2>
      <div class="project-content">
        <img
          class="project-image"
          src="assets/img/shorts_qr_code.svg"
          @click="toggleQR('shorts')"
        >
        <div class="project-description">
          <h3>一個極簡的短網址伺服器 </h3>
          <p>用一個檔案定義短連結，提供統計數據</p>
          <a href="https://github.com/NTUT-NPC/shorts/">
            原始碼
          </a>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.project-content {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
}

.project-image {
  width: 100%;
  min-width: 200px;
  max-width: 300px;
  max-height: 300px;
  border-radius: 2rem;
  object-fit: contain;
}

.project-description {
  flex: 1;
  min-width: 200px;
}

.project-description p {
  margin: 0 0 1rem;
}

.download-badge {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 2rem;
  flex-wrap: wrap;
  img {
    height: 50px;
    transition: transform 0.3s;
    &:hover {
      transform: scale(1.05);
    }
  }
}
</style>
