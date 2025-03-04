<script>
export default {
  name: 'DC',
  props: {
    userId: {
      type: String,
      required: true,
    },
  },
  computed: {
    href() {
      return `https://discord.com/users/${this.userId}`
    },
  },
}
</script>

<template>
  <a
    class="dc-at"
    :href="href"
    target="_blank"
  >
    <slot />
  </a>
</template>

<style scoped>
.dc-at {
  background-color: #40447e;
  color: white;
  font-weight: 700;
  padding: 0.1rem 0.3rem;
  border-radius: 0.3rem;
}
</style>
