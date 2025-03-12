<script>
export default {
  data() {
    return {
      resourceLinks: [
        { id: 1, name: '社課報名表單', url: 'https://to.ntut.club/latest', icon: 'https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.flaticon.com%2Ffree-icon%2Fgoogle-forms_5968528&psig=AOvVaw0VXJqO8bKep-7UveJMTYzV&ust=1741847521463000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCOCjp-j1g4wDFQAAAAAdAAAAABAE', img: 'https://ugc.production.linktr.ee/874f245f-c690-4c79-9462-21b3ddbafe39_--.png?io=true&size=thumbnail-feature-v1_0' },
        { id: 2, name: 'Discord 伺服器', url: '/discord', icon: 'https://ugc.production.linktr.ee/ae7e80b0-de1d-4df0-ba37-fd1bc26619cf_discord.webp?io=true&size=thumbnail-stack-v1_0' },
        { id: 3, name: 'TAT - 北科生活', url: '/tat', icon: '/_nuxt/assets/img/tat.webp' },
        { id: 4, name: 'Blog', url: '/blog' },
      ],
      socialMediaLinks: [
        { id: 1, name: 'Instagram', url: '/ig', icon: 'https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Instagram_logo_2016.svg/132px-Instagram_logo_2016.svg.png' },
        { id: 2, name: 'Instagram', url: '/ig', icon: 'https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Instagram_logo_2016.svg/132px-Instagram_logo_2016.svg.png' },
        { id: 3, name: 'Instagram', url: '/ig', icon: 'https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Instagram_logo_2016.svg/132px-Instagram_logo_2016.svg.png' },
        { id: 4, name: 'Instagram', url: '/ig', icon: 'https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Instagram_logo_2016.svg/132px-Instagram_logo_2016.svg.png' },
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
    <div
      id="icons-container"
    >
      <div
        v-for="socialMedia in socialMediaLinks"
        :key="socialMedia.id"
      >
        <NuxtLink
          class="icon"
          :to="socialMedia.url"
        >
          <img
            :alt="socialMedia.name"
            :src="socialMedia.icon"
          >
        </NuxtLink>
      </div>
    </div>
    <div id="links-container">
      <div
        v-for="resourceLink in resourceLinks"
        :key="resourceLink.id"
      >
        <NuxtLink
          class="link"
          :to="resourceLink.url"
        >
          <div class="text-container">
            <img
              v-if="!resourceLink.img"
              alt=""
              class="icon"
              :src="resourceLink.icon"
            >
            <h3>
              {{ resourceLink.name }}
            </h3>
          </div>
          <img
            alt=""
            :src="resourceLink.img"
          >
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
.npc-paragraph {
  max-width: 500px;
}
.profile-image {
  width: 6rem;
  height: 6rem;
  object-fit: cover;
  border-radius: 50%;
  margin-bottom: 2rem;
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
    margin-bottom: 1rem;
    text-align: center;
  }
}
.link {
  background-color: var(--box-background-color);
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 1rem;
  padding: 1rem;
  border-radius: 1rem;
  transition: transform 0.1s;
  &:hover {
    transform: scale(1.01);
    transition: transform 0.1s;
  }
  img {
    border-radius: 1rem;
  }
}
.text-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  img {
    position: relative;
    margin: auto;
    width: 3rem;
    object-fit: contain;
    border-radius: 0.5rem;
  }
  h3 {
    width: 100%;
    text-align: center;
    margin: 0;
  }
}

#icons-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
  img {
    width: 3rem;
    object-fit: contain;
    border-radius: 0.5rem;
  }
  a {
    cursor: pointer;
  }
}
</style>
