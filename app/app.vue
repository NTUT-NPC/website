<script setup lang="ts">
import { breakpointsSematic } from '@vueuse/core'
import IconClose from '~icons/mingcute/close-fill'
import IconDiscord from '~icons/mingcute/discord-fill'
import IconGitHub from '~icons/mingcute/github-fill'
import IconMenu from '~icons/mingcute/menu-fill'
import IconMoon from '~icons/mingcute/moon-fill'

import 'assets/reset.css'
import 'assets/cubic-11.css'

useHead({
  title: '北科程式設計研究社',
  link: [
    { rel: 'manifest', href: '/manifest.webmanifest' },
    { rel: 'icon', href: '/favicon.ico', sizes: '32x32' },
    { rel: 'icon', href: '/icon.svg', type: 'image/svg+xml' },
    { rel: 'apple-touch-icon', href: '/apple-touch-icon.png' },
  ],
})

const isDark = useDark()
const toggleDark = useToggle(isDark)

const routes = {
  '/': '關於',
  '/projects': '專案',
  '/join': '加入我們',
  '/contact': '聯絡資訊',
}

const breakpoints = useBreakpoints(breakpointsSematic)
const isMobile = breakpoints.smaller('tablet')

const [mobileMenuOpen, toggleMobileMenu] = useToggle(false)
</script>

<template>
  <NuxtRouteAnnouncer />

  <header id="header">
    <div class="left">
      <a href="/">
        <img src="assets/img/npc-horizontal.svg">
      </a>
    </div>

    <template v-if="isMobile">
      <div class="right">
        <ul>
          <li>
            <button @click="toggleMobileMenu()">
              <IconClose v-if="mobileMenuOpen" />
              <IconMenu v-else />
            </button>
          </li>
        </ul>
      </div>
    </template>

    <template v-else>
      <nav class="center">
        <ul>
          <li
            v-for="(route, path) in routes"
            :key="path"
          >
            <NuxtLink :to="path">
              {{ route }}
            </NuxtLink>
          </li>
        </ul>
      </nav>

      <div class="right">
        <ul>
          <li>
            <a
              href="https://to.ntut.club/discord"
              target="_blank"
            ><IconDiscord /></a>
          </li>
          <li>
            <a
              href="https://github.com/NTUT-NPC"
              target="_blank"
            ><IconGitHub /></a>
          </li>
          <li>
            <button @click="toggleDark()">
              <IconMoon />
            </button>
          </li>
        </ul>
      </div>
    </template>
  </header>

  <Transition name="menu">
    <menu
      v-if="mobileMenuOpen"
      id="header-mobile-menu"
    >
      <li
        v-for="(name, path) in routes"
        :key="path"
      >
        <NuxtLink
          class="mobile-menu-route"
          :to="path"
          @click="toggleMobileMenu()"
        >
          {{ name }}
        </NuxtLink>
      </li>
      <div class="separator" />
      <li>
        <a
          href="https://to.ntut.club/discord"
          target="_blank"
        ><IconDiscord />Discord</a>
      </li>
      <li>
        <a
          href="https://github.com/NTUT-NPC"
          target="_blank"
        ><IconGitHub />GitHub</a>
      </li>
      <div class="separator" />
      <li>
        <button @click="() => { toggleDark(); toggleMobileMenu(); }">
          <IconMoon />深色主題
        </button>
      </li>
    </menu>
  </Transition>

  <NuxtPage />
</template>

<style>
:root {
  --background-color: #f8f9fa;
  --text-color: #333333;
  --heading-color: #000000;
  --button-background-color: #e4e4e4;
  --button-hover-background-color: #cccccc;
  --box-background-color: #ffffff;
  --box-shadow-color: 0 0 1rem rgba(0, 0, 0, 0.1);
  --link-color: rgb(0, 115, 255);
  --link-hover-color: rgb(0, 83, 184);
}

.dark {
  --background-color: #222222;
  --text-color: #e0e0e0;
  --heading-color: #ffffff;
  --button-background-color: #444444;
  --button-hover-background-color: #666666;
  --box-background-color: #2a2a2a;
  --box-shadow-color: 0 0 1rem rgba(0, 0, 0, 0.1);
  --link-color: rgb(0, 221, 255);
  --link-hover-color: rgb(65, 150, 255);
}

html {
  background-color: var(--background-color);
  color: var(--text-color);
  font-family: 'Arial', sans-serif;
}

h1 {
  color: var(--heading-color);
  display: block;
  font-size: 2.5rem;
  margin-top: 0.67em;
  margin-bottom: 0.67em;
  margin-left: 0;
  margin-right: 0;
  font-weight: bold;
}

h2 {
  color: var(--heading-color);
  display: block;
  font-size: 2rem;
  margin-top: 0.83em;
  margin-bottom: 0.83em;
  margin-left: 0;
  margin-right: 0;
  font-weight: bold;
}

h3 {
  color: var(--heading-color);
  display: block;
  font-size: 1.5rem;
  margin-top: 1em;
  margin-bottom: 1em;
  margin-left: 0;
  margin-right: 0;
  font-weight: bold;
}

p {
  color: var(--text-color);
  display: block;
  margin-left: 0;
  margin-right: 0;
}

a {
  color: var(--link-color);
  text-decoration: none;
  transition: color 0.3s;
  &:hover {
    color: var(--link-hover-color);
  }
}

ul {
  display: block;
  list-style-type: disc;
  margin-top: 1rem;
  margin-bottom: 1rem;
  margin-left: 0;
  margin-right: 0;
  padding-left: 40px;
  li {
    display: list-item;
  }
}

button {
  background-color: var(--button-background-color);
  color: var(--text-color);
  border: none;
  padding: 0.75rem 1.5rem;
  border-radius: 5px;
  cursor: pointer;
  box-shadow: 0 2px 5px var(--box-shadow-color);
  transition: background-color 0.3s;

  &:hover {
    background-color: var(--button-hover-background-color);
  }
}

.npc-paragraph {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 2rem 0.5rem;
  margin: auto;
  /* border-radius: 8px; */
  max-width: 1000px;
  & > div {
    gap: 0;
  }
}

.npc-box {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  padding: 2rem;
  margin: auto;
  border-radius: 8px;
  width: 100%;
  background-color: var(--box-background-color);
  box-shadow: var(--box-shadow-color);

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
    /* object-fit: cover; */
    border-radius: 2rem;
    object-fit: contain;
  }

  .project-description {
    flex: 1;
    min-width: 200px;
  }

  .project-description p {
    margin: 0 0 1rem;
  }
}

.shadow {
  box-shadow: rgba(131, 131, 131, 0.479) 1px 1px 40px;
}

#header,
#header-mobile-menu {
  background-color: #333 !important;
  /* color: white !important; */

  ul,
  & {
    display: flex;
    gap: 0.5rem;
    padding: 0;
    > li {
      display: flex;
      align-items: center;
      list-style: none;

      &:hover {
        cursor: pointer !important;
        background-color: #fff3 !important;
      }
    }
  }

  button,
  a {
    all: unset;
    display: flex;
    padding: 0.5rem;
    color: white !important;
    & > svg {
      height: 3rem;
    }
  }
}

#header {
  font-family: 'Cubic 11';
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 4rem;
  padding: 0.5rem 2rem;

  > * {
    flex: 1;
    display: flex;
    align-items: center;
  }

  > .left img {
    height: 2rem;
  }

  > .center {
    justify-content: center;

    .router-link-active {
      text-decoration: underline;
      text-underline-offset: 0.5rem;
    }
  }

  > .right {
    justify-content: flex-end;
  }
}

.menu-enter-from,
.menu-leave-to {
  opacity: 0;
  transform: translateY(-1rem);
}

#header-mobile-menu {
  position: absolute;
  inset: 4rem 0 0 0;
  display: flex;
  flex-direction: column;
  padding: 1.5rem;
  gap: 1.5rem;
  font-size: 2rem;
  transition: all 0.4s ease;

  li {
    display: flex;
    align-items: center;

    > * {
      all: unset;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.25rem 0.5rem;
      width: 100%;
      height: 100%;
    }
  }

  .mobile-menu-route {
    &::before {
      content: '◆';
      display: inline-block;
      visibility: hidden;
    }
    &.router-link-active::before {
      visibility: visible;
    }
  }

  .separator {
    border-top: calc(1em / 11) solid darkgray;
  }
}
</style>
