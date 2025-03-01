<script>
export default {
  data() {
    return {
      name: '',
      num: '',
      dep: '',
      classroom: '共科 312',
      day: '二',
    }
  },
  computed: {
    formUrl() {
      return 'https://docs.google.com/forms/d/e/1FAIpQLSciz2ZVjV-yBNIurfYDtsof0ZSiqwXm0-oQlxZwwdmp6wnF_Q/viewform?usp=pp_url'
    },
  },
}
</script>

<template>
  <div class="npc-paragraph">
    <div class="npc-box">
      <strong>
        <h2>
          入社流程
        </h2>
      </strong>
      <div class="project-content">
        <div class="project-description">
          <p>
            首先請加入 <a
              href="https://to.ntut.club/discord"
              target="_blank"
            >Discord 群組</a>，並且在下方填寫入社申請表單
          </p>
          <form
            :action="formUrl"
            method="GET"
            target="_blank"
          >
            <label>
              姓名：
              <input
                id="name"
                v-model="name"
                name="entry.709574167"
                placeholder="王大同"
                type="text"
              >
            </label>
            <label>
              學號：
              <input
                id="num"
                v-model="num"
                name="entry.781375275"
                placeholder="112345678"
                type="text"
              >
            </label>
            <label>
              系級：
              <input
                id="dep"
                v-model="dep"
                name="entry.458858603"
                placeholder="電資十"
                type="text"
              >
            </label>
            <button type="submit">
              前往申請表
            </button>
          </form>
          <br>
          <p>
            可於禮拜{{ day }}社課期間至<strong>{{ classroom }}</strong> 或於平日中午到 <NuxtLink to="/contact">
              社團辦公室
            </NuxtLink> 繳費
          </p>
          <p>繳費完將立即啟用 Discord 社員身份</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
form {
  display: grid;
  gap: 1.5rem;
  input {
    background-color: transparent;
    border: 0;
    /* border-bottom: var(--text-color) solid 1px; */
    color: var(--text-color);
  }
}
</style>
