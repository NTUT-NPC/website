<script>
export default {
  data() {
    return {
      showQR: false,
    }
  },
  methods: {
    toggleQR() {
      this.showQR = !this.showQR
    },
  },
}
</script>

<template>
  <div class="npc-paragraph">
    <h1>專案</h1>
    <div class="npc-box">
      <h2>TAT - 北科生活</h2>
      <div class="project-content">
        <img
          v-if="!showQR"
          class="project-image image-shadow"
          src="https://i.imgur.com/pMSmPA8.webp"
        >
        <img
          v-if="showQR"
          id="tat-qr"
          class="project-image image-shadow"
          src="https://files.ntut.club/projects/tat/qrcode.png"
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
            src="assets/Download_on_the_App_Store_Badge_CNTC_RGB_blk_100217.svg"
          >
        </a>
        <a href="https://to.ntut.club/tat/android">
          <img
            alt="Get it on Google Play"
            src="assets/GetItOnGooglePlay_Badge_Web_color_Chinese-TW.png"
          >
        </a>
      </div>
      <label @click="toggleQR">顯示 QR 碼</label>
    </div>

    <div class="npc-box">
      <h2>Shorts - 短褲</h2>
      <div class="project-content">
        <img
          class="project-image"
          src="https://github.com/NTUT-NPC/shorts/raw/main/docs/shorts.svg"
        >
        <div class="project-description">
          <h3>一個極簡的短網址伺服器 </h3>
          <p>用一個檔案定義短連結，提供統計數據</p>
          <a href="https://github.com/NTUT-NPC/shorts/">
            原始碼
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
