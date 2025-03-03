<template>
  <div class="npc-paragraph">
    <h1>北科程式設計研究社</h1>
    <div class="npc-box">
      <h2>關於我們</h2>
      <p>由一群熱愛程式設計的學生所組成的社團</p>
      <p>扭轉迷思，提供許多管道給想要學習程式的你！</p>

      <div />

      <button @click="$router.push('/join')">
        加入我們
      </button>
    </div>
  </div>
</template>

<style scoped>
button {
  margin-top: 1rem;
}
</style>
