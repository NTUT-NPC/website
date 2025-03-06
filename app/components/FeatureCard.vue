<script setup lang="ts">
defineProps<{
  title: string
  imageSrc?: string
  imageAlt?: string
  toggleFn?: () => void
}>()
</script>

<template>
  <section class="card">
    <h2>{{ title }}</h2>
    <div class="project-content">
      <img
        :alt="imageAlt || ''"
        class="project-image"
        :src="imageSrc || ''"
        @click="toggleFn && toggleFn()"
      >
      <div class="project-description">
        <slot name="description" />
      </div>
    </div>
    <slot name="footer" />
  </section>
</template>

<style scoped>
.project-content {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
}

.project-image {
  width: 100%;
  min-width: 200px;
  max-width: 300px;
  max-height: 300px;
  border-radius: 2rem;
  object-fit: contain;
}

.project-description {
  flex: 1;
  min-width: 200px;

  p {
    margin: 0 0 1rem;
  }
}
</style>
