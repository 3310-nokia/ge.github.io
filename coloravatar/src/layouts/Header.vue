<template>
  <header class="header">
    <Logo />

    <h2 class="site-title">GEAV</h2>

    <div class="header-right">
      <a
        href="https://pump.fun/board"
        target="_blank"
        rel="nofollow noopener noreferrer"
      >
        <button
          type="button"
          class="github-button"
          @click="
            recordEvent('click_github', {
              event_category: 'click',
            })
          "
        >
          <img :src="IconGitHub" alt="GitHub" />
          <span class="text">CA:TBA···</span>
        </button>
      </a>
    </div>
  </header>
</template>

<script lang="ts" setup>
import IconGitHub from '@/assets/icons/icon-github.svg'
import Logo from '@/components/Logo.vue'
import { recordEvent } from '@/utils/ga'
</script>

<style lang="scss" scoped>
@use 'src/styles/var';

.header {
  display: flex;
  align-items: center;
  height: var.$layout-header-height;
  padding: 1rem 2rem;

  .site-title {
    margin-left: 1rem;
    font-weight: bold;
    font-size: 1.9rem;
    cursor: default;

    @media screen and (max-width: var.$screen-sm) {
      display: none;
    }
  }

  .header-right {
    margin-left: auto;

    .github-button {
      position: relative;
      z-index: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 12rem;
      height: 2.6rem;
      overflow: hidden;
      color: var.$color-text;
      font-weight: bold;
      font-size: 1.05rem;
      background-color: var.$color-dark;
      border-radius: 0.6rem;
      cursor: pointer;
      user-select: none;

      &:hover {
        background-color: darken(var.$color-dark, 3);
      }
      img {
      width: 1.5rem;
      height: 1.5rem; 
      }
  
      .text {
        margin-left: 0.2rem;
        letter-spacing: 0.03rem;
      }
    }
  }
}
</style>
