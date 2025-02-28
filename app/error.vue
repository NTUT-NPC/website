<script setup>
const router = useRouter()
const { currentRoute } = router
const currentPath = currentRoute.value.fullPath
const targetUrl = `https://to.ntut.club/api/try?slug=${currentPath}&fallback=${location.protocol}//${location.host}/404`

onMounted(() => {
  window.location.href = targetUrl
})
</script>
