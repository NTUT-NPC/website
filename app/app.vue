<script setup lang="ts">
import { breakpointsSematic } from '@vueuse/core'
import IconClose from '~icons/mingcute/close-fill'
import IconDiscord from '~icons/mingcute/discord-fill'
import IconGitHub from '~icons/mingcute/github-fill'
import IconMenu from '~icons/mingcute/menu-fill'
import IconMoon from '~icons/mingcute/moon-fill'

import 'assets/reset.css'
import 'assets/cubic-11.css'
import 'assets/style.css'
import 'assets/global.css'

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
        <img src="assets/npc-horizontal.svg">
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
