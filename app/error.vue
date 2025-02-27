<script setup>
const router = useRouter()
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
    <NuxtLink to="/">
      返回首頁
    </NuxtLink>
    <br>
    <br>
    <NuxtLink :to="targetUrl">
      <button>
        嘗試在 <strong>Shorts 短網址</strong>尋找此路徑
      </button>
    </NuxtLink>
  </div>
</template>

<style scoped>
  .error-page {
  text-align: center;
  padding: 4rem;
}
</style>
