<template>
  <nav
    class="navbar"
    :class="[
      { 'navbar-expand-lg': expand },
      { [`navbar-${effect}`]: effect },
      { 'navbar-transparent': transparent },
      { [`bg-${type}`]: type },
      { rounded: round },
    ]"
  >
    <div class="container">
      <slot name="container-pre"></slot>
      <slot name="brand">
        <a class="navbar-brand" href="#" @click.prevent="onTitleClick">
          {{ title }}
        </a>
      </slot>
      <navbar-toggle-button
        :toggled="toggled"
        :target="contentId"
        @click.native.stop="toggled = !toggled"
      >
      </navbar-toggle-button>

      <slot name="container-after"></slot>
      <transition name="slide">
        <div
          class="collapse navbar-collapse"
          :class="{ show: toggled }"
          :id="contentId"
          v-click-outside="closeMenu"
          v-if="isPanelOpen"
        >
          <div class="navbar-collapse-header">
            <slot name="content-header" :close-menu="closeMenu"></slot>
          </div>
          <slot :close-menu="closeMenu"></slot>
        </div>
      </transition>
    </div>
  </nav>
</template>
<script>
import { FadeTransition } from 'vue2-transitions';
import NavbarToggleButton from './NavbarToggleButton';
import { store, mutations } from '@/store.js';

export default {
  name: 'base-nav',
  components: {
    FadeTransition,
    NavbarToggleButton,
  },
  props: {
    type: {
      type: String,
      default: 'primary',
      description: 'Navbar type (e.g default, primary etc)',
    },
    title: {
      type: String,
      default: '',
      description: 'Title of navbar',
    },
    contentId: {
      type: [String, Number],
      default: Math.random().toString(),
      description:
        "Explicit id for the menu. By default it's a generated random number",
    },
    effect: {
      type: String,
      default: 'dark',
      description: 'Effect of the navbar (light|dark)',
    },
    round: {
      type: Boolean,
      default: false,
      description: 'Whether nav has rounded corners',
    },
    transparent: {
      type: Boolean,
      default: false,
      description: 'Whether navbar is transparent',
    },
    expand: {
      type: Boolean,
      default: false,
      description: 'Whether navbar should contain `navbar-expand-lg` class',
    },
  },
  data() {
    return {
      toggled: false,
    };
  },
  computed: {
    isPanelOpen() {
      return store.isNavOpen;
    },
  },
  methods: {
    closeSidebarPanel: mutations.toggleNav,

    onTitleClick(evt) {
      this.$emit('title-click', evt);
    },
    closeMenu() {
      this.toggled = false;
    },
  },
};
</script>
<style lang="scss">
  .navbar-collapse.show {
    height: 100vh;
    opacity: 1;
  }
// Keyframes
@keyframes show-navbar-collapse {
  0% {
    opacity: 0;
    height: 0;
    transform: scale(0.95);
    transform-origin: 100% 0;
  }
  100% {
    opacity: 1;
    height: 100;
    transform: scale(1);
  }
}
@keyframes hide-navbar-collapse {
  from {
    opacity: 1;
    height: 100;
    transform: scale(1);
    transform-origin: 100% 0;
  }
  to {
    opacity: 0;
    height: 0;
    transform: scale(0.95);
  }
}
@keyframes show-navbar-dropdown {
  0% {
    opacity: 0;
    transform: translate(0, 10px) perspective(200px) rotateX(-2deg);
    transition: visibility 0.25s, opacity 0.25s, transform 0.25s;
  }
  100% {
    transform: translate(0, 0);
    opacity: 1;
  }
}
@keyframes hide-navbar-dropdown {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
    transform: translate(0, 10px);
  }
}
.slide-enter-active,
.slide-enter {
    animation: show-navbar-collapse 0.5s ease forwards;
}

.slide-leave-active,
.slide-leave-to {
   animation: hide-navbar-collapse 0.5s ease forwards;
}
</style>
