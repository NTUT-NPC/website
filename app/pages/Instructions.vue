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
            >Discord 伺服器</a>，並透過以下幾種方式聯絡我們
          </p>
          <a
            href="https://to.ntut.club/discord"
            target="_blank"
          >
            <div class="discord-channel">
              <svg
                aria-hidden="true"
                class="icon__2ea32"
                fill="none"
                height="24"
                role="svg"
                viewBox="0 0 24 24"
                width="24"
                xmlns="http://www.w3.org/2000/svg"
              ><path
                class=""
                clip-rule="evenodd"
                d="M15 2a3 3 0 0 1 3 3v12H5.5a1.5 1.5 0 0 0 0 3h14a.5.5 0 0 0 .5-.5V5h1a1 1 0 0 1 1 1v15a1 1 0 0 1-1 1H5a3 3 0 0 1-3-3V5a3 3 0 0 1 3-3h10Zm-.3 5.7a1 1 0 0 0-1.4-1.4L9 10.58l-2.3-2.3a1 1 0 0 0-1.4 1.42l3 3a1 1 0 0 0 1.4 0l5-5Z"
                fill="currentColor"
                fill-rule="evenodd"
              /></svg>
              <strong>北科程式設計研究社</strong>
            </div>
          </a>
          <ul>
            <li>
              <h4>
                Instagram <a href="https://instagram.com/npc.designer">@npc.designer</a>
              </h4>
            </li>

            <li>
              <h4>
                於社課期間到上課教室
              </h4>
            </li>
            <li>
              <h4>
                Discord 伺服器首頁點選私訊 <DC user-id="1171113302739394628">
                  @小N
                </DC>
              </h4>
            </li>
            <li>
              <h4>
                Email <a href="mailto:contact@ntut.club">contact@ntut.club</a>
              </h4>
            </li>
          </ul>
          <br>
          <p>並告訴我們你的 <strong>姓名</strong>、<strong>學號</strong> 和 <strong>Discord 使用者名稱</strong>，我們將為您安排時間繳費與領取社服</p>
        </div>
      </div>
      <NuxtLink to="/join">
        <button>
          返回
        </button>
      </NuxtLink>
    </div>
  </div>
</template>

<style scoped>
.discord-channel {
  display: flex;
  align-items: center;
  background-color: #353535;
  width: fit-content;
  padding: 0.3rem 0.5rem;
  border-radius: 0.5rem;
  margin: 0.5rem;
  cursor: pointer;
  svg {
    margin-right: 0.5rem;
    color: white;
  }
  strong {
    margin-right: 2rem;
    color: white;
  }
  &:hover {
    background-color: #494949;
    transform: scale(1.02);
  }
}
.dc-at {
  background-color: #40447e;
  color: white;
  font-weight: 700;
  padding: 0.1rem 0.3rem;
  border-radius: 0.3rem;
}
</style>
