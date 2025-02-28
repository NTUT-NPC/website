<script setup>
const router = useRouter()
const isDark = useDark()
const { currentRoute } = router
const currentPath = currentRoute.value.fullPath
const targetUrl = `https://to.ntut.club${currentPath}`
// async function checkUrl() {
//   const response = await fetch(targetUrl, { method: 'GET' });
//   if(response.ok){
//     console.log(targetUrl);
//     window.location.href = targetUrl;
//   }
// }

// onMounted(() => {
//   checkUrl();
// })
</script>

<template>
  <div class="error-page">
    <h1>404 - 找不到頁面</h1>
    <p>抱歉，<strong>小N</strong>找不到您所請求的頁面：<br><a href="#">https://ntut.club{{ currentPath }}</a></p>
    <NuxtLink :to="targetUrl">
      <button>
        嘗試在 <strong>Shorts 短網址</strong>尋找此路徑
      </button>
    </NuxtLink>
    <br>
    <br>
    <NuxtLink to="/">
      返回首頁
    </NuxtLink>
  </div>
  <img
    alt="小 N 在哭"
    class="np-cat"
    src="assets/img/n.png"
  >
  <div class="theme-switcher">
    <button @click="isDark = 0">
      <img
        alt="Light"
        src="assets/img/light_mode.svg"
      >
    </button>
    <button @click="isDark = 1">
      <img
        alt="Dark"
        src="assets/img/dark_mode.svg"
      >
    </button>
  </div>
</template>

<style scoped>
.error-page {
  text-align: center;
  padding: 4rem;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.np-cat {
  position: absolute;
  right: 0;
  bottom: 0;
  max-width: 50dvw;
  max-height: 60dvh;
}

.theme-switcher {
  position: absolute;
  bottom: 1rem;
  left: 1rem;
  background-color: #ececec;
  border: 1px solid rgb(145, 145, 145);
  border-radius: 0.5rem;
  padding: 0;
  animation: fadeIn 0.5s ease-out;
  button {
    margin: 0;
    background-color: transparent;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 0.5rem;
    &:hover {
      background-color: rgba(0, 0, 0, 0.274);
      img {
        transition:
          transform 0.2s ease,
          background-color 0.2s ease;
        transform: scale(1.15);
        filter: invert(100%) sepia(100%) saturate(1%) hue-rotate(221deg) brightness(109%) contrast(101%);
      }
      &:active {
        transform: scale(0.9);
      }
    }
  }
}
</style>
