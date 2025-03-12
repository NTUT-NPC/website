<script>
export default {
  data() {
    return {
      links: [
        { id: 1, name: 'Home', url: '/' },
        { id: 2, name: 'About', url: '/about' },
        { id: 3, name: 'Contact', url: '/contact' },
        { id: 4, name: 'Blog', url: '/blog' },
      ],
    }
  },
}
</script>

<template>
  <div class="npc-paragraph">
    <div class="profile-info">
      <img
        alt="avatar"
        class="profile-image"
        src="assets/img/shorts.svg"
      >
      <h1>北科程式設計研究社 NPC</h1>
      <h2>串聯志同道合的人，共創熱愛科技的社群，探索和發展新技能。</h2>
    </div>
    <div id="icons-container">
      <ul>
        <li />
        <li />
        <li />
        <li />
        <li />
      </ul>
    </div>
    <div id="links-container">
      <div
        v-for="link in links"
        :key="link.id"
      >
        <NuxtLink
          class="link"
          :to="link.url"
        >
          <h3>
            {{ link.name }}
          </h3>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
    .profile-image {
  width: 200px;
  height: 200px;
  border-radius: 50%;
}
.profile-info {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  h1 {
    font-size: 2rem;
    margin: 0;
  }
  h2 {
    font-size: 1rem;
    margin: 0;
  }
}
.link {
  background-color: rgb(191, 191, 191);
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin: 1rem;
  padding: 1rem;
  border-radius: 1rem;
  transition: transform 0.1s;
  h3 {
    margin: 0;
  }
  &:hover {
    transform: scale(1.01);
    transition: transform 0.1s;
  }
}
</style>
