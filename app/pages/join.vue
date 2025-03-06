<script setup lang="ts">
import DiscordQrCode from '~/assets/img/discord_qr_code.svg'
import TShirtImage from '~/assets/img/t-shirt.webp'
import FeatureCard from '~/components/FeatureCard.vue'
</script>

<template>
  <article class="container">
    <FeatureCard
      image-alt="社團T恤"
      :image-src="TShirtImage"
      title="社員"
    >
      <template #description>
        <h3>🌟 加入我們的社團吧！🌟</h3>
        <p>🎉 成為 <strong>我們的一員</strong>，您將獲得：</p>
        <ul>
          <li>獨家社服一件，展現您的團隊精神！</li>
          <li>精彩的社課，提升您的技能與知識！</li>
          <li>永久社員資格，一次繳費，終身受用！</li>
        </ul>
        <br>
        <p>💰 社費僅需 500 元，讓您享受所有會員專屬福利！</p>
        <p>📢 建議加入我們的 Discord 群組，隨時掌握最新消息與活動資訊，與其他會員互動交流！</p>
        <p>快來加入我們的大家庭，一起創造美好的回憶！💖</p>
        <p>有興趣的朋友請點擊下方 Discord 連結，或透過 Email 聯絡我們！</p>
        <p>歡迎來社課或社辦繳費</p>
      </template>
      <template #footer>
        <div class="join-button-container">
          <a href="https://to.ntut.club/discord">
            <button class="btn-discord">
              <strong>加入 Discord</strong>
            </button>
          </a>
          <a href="mailto:contact@ntut.club">
            <button>Email</button>
          </a>
        </div>
      </template>
    </FeatureCard>

    <FeatureCard
      image-alt="Discord QR Code"
      :image-src="DiscordQrCode"
      title="線上成員"
    >
      <template #description>
        <h3>
          還在猶豫嗎？先加入 Discord 群組吧！
        </h3>
        <p>加入社群，您將獲得：</p>
        <ul>
          <li>公開頻道存取權限！</li>
          <li>與電神交流的機會！</li>
          <li>了解更多社團活動！</li>
        </ul>
        <br>
        <a href="https://to.ntut.club/discord"><button class="btn-discord">
          <strong>
            加入 Discord
          </strong>
        </button></a>
        <p>💰 好吃的古早味社課，每次只要 50 元，歡迎來看看！</p>
      </template>
    </FeatureCard>
  </article>
</template>

<style scoped>
.join-button-container {
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

.btn-discord {
  background-color: #0071e3;
  color: white;

  &:hover {
    background-color: #692ae6;
    color: white;
  }
}
</style>
