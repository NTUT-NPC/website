<script setup>
const router = useRouter()
const { currentRoute } = router
let currentPath = currentRoute.value.fullPath
if (currentPath === '/') {
  currentPath = ''
} else {
  if (currentPath[0] === '/') {
    currentPath = currentPath.slice(1)
  }
  if (currentPath[currentPath.length - 1] === '/') {
    currentPath = currentPath.slice(0, -1)
  }
}
const targetUrl = `https://to.ntut.club/api/try?slug=${currentPath}&fallback=${location.protocol}//${location.host}/404`

onMounted(() => {
  window.location.href = targetUrl
})
</script>
