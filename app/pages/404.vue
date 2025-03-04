<template>
  <div class="npc-paragraph">
    <h1>哎呀～似乎迷路了！</h1>
    <div class="error-description">
      <p>小N 正在這裡悠哉散步，但您要找的頁面卻不在這裡。可能的原因：</p>
      <ul style="text-align: left; display: inline-block;">
        <li>網址輸入錯誤</li>
        <li>該頁面已被移除或改名</li>
        <li>您在尋找另一個祕密角落？</li>
      </ul>
      <p>不用擔心，讓小N 為您指引方向：</p>
    </div>
    <NuxtLink
      class="home-button"
      to="/"
    >
      返回首頁
    </NuxtLink>
  </div>

  <img
    alt="小 N 在哭"
    class="np-cat"
    draggable="false"
    src="assets/img/np-cat.webp"
  >
</template>

<style scoped>
.npc-paragraph {
  max-width: 600px;
  padding: 0 2rem;
  h1 {
    align-self: center;
    margin-top: 2.5rem;
    margin-bottom: 1rem;
  }
}

.error-description {
  display: flex;
  flex-direction: column;
}

.np-cat {
  position: absolute;
  right: 0;
  bottom: 0;
  max-width: 40dvw;
  max-height: 40dvh;
  z-index: -1;
}

.home-button {
  margin-top: 1.2em;
  font-weight: 500;
  background-color: #00ddff;
  color: rgb(43, 42, 51);
  padding: 0.5rem 1.5rem;
  border-radius: 0.25rem;
  display: block;
  margin-left: auto;
  transition: 10s;
}

ul {
  margin-bottom: 1rem;
}
</style>
