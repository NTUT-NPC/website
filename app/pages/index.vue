<template>
  <div class="npc-paragraph">
    <h1>北科程式設計研究社</h1>
    <div class="h-box-container">
      <div class="npc-h-box">
        <h2>推廣資訊技術</h2>
        <p>我們致力於在北科校園推廣資訊技術，開設多種程式語言課程，讓更多人體驗程式的魅力。</p>
      </div>
      <div class="npc-h-box">
        <h2>多樣化活動</h2>
        <p>每學期我們會舉辦社課、社聚、跨校交流及黑客松等活動，並提供基礎課程幫助初學者快速上手。</p>
      </div>
      <div class="npc-h-box">
        <h2>專案開發</h2>
        <p>我們鼓勵社員參加讀書會和團隊合作，最終進入專案的開發，讓每個人都能在實踐中學習和成長。</p>
      </div>
      <div class="npc-h-box">
        <h2>樹莓派！</h2>
        <p>我們有 7 片樹莓派 5B！！</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
h1 {
  text-align: center;
}
h2 {
  text-align: center;
  margin-bottom: 0;
  width: 100%;
  height: fit-content;
}
p {
  /* text-align: center; */
  margin-top: 0;
  height: fit-content;
}
button {
  margin-top: 1rem;
}
.h-box-container {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  justify-content: center;
}
.npc-h-box {
  display: flex;
  flex: 1;
  gap: 1rem;
  flex-wrap: wrap;
  justify-content: center;
  background-color: var(--box-background-color);
  border-radius: 1rem;
  padding: 1rem;
  margin: 0.5rem;
  min-width: 15rem;
  box-shadow: var(--box-shadow-color);
}
.rpi {
  width: 100%;
}
</style>
