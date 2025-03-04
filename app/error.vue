<script setup lang="ts">
import { onMounted } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()

function normalizePath(fullPath: string): string {
  if (fullPath === '/') return ''
  let path = fullPath

  if (path.startsWith('/')) {
    path = path.slice(1)
  }
  if (path.endsWith('/')) {
    path = path.slice(0, -1)
  }
  return path
}

const slug = normalizePath(route.fullPath)
const fallbackUrl = `${location.protocol}//${location.host}/not-found?url=${window.location.href}`
const targetUrl = `https://to.ntut.club/api/try?slug=${slug}&fallback=${fallbackUrl}`

onMounted(() => {
  window.location.replace(targetUrl)
})
</script>
