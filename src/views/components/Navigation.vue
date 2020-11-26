<template>
  <section class="">
    <div class="container">
      <!-- Navigation -->
      <h2 class="mb-5">
        <span>Navbars</span>
      </h2>
    </div>
    <!-- Navbar default -->
    <base-nav
      v-for="menu in menus"
      :key="menu.type"
      :type="menu.type"
      effect="dark"
      expand
      title="Default Color"
      class="mt-4"
      :content-id="`navbar-${menu.type}`"
    >
      <div class="row" slot="content-header" slot-scope="{ closeMenu }">
        <div class="col-6 collapse-brand">
          <a href="./index.html">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 217.21 37.69">
              <g id="Ebene_2" data-name="Ebene 2">
                <g id="Ebene_1-2" data-name="Ebene 1">
                  <path
                    d="M123.4,30.42a5.36,5.36,0,0,1-5.32,4.88l-.48,0a5.35,5.35,0,1,1,4.57-8.76A5.27,5.27,0,0,1,123.4,30.42Z"
                  />
                  <path
                    d="M138.39,31.88A5.66,5.66,0,0,1,132.78,37a4.36,4.36,0,0,1-.51,0,5.64,5.64,0,1,1,4.83-9.24A5.56,5.56,0,0,1,138.39,31.88Z"
                  />
                  <path
                    d="M212.42,37.69a4.79,4.79,0,0,1-4.79-4.79V9.58H9.58V32.9A4.79,4.79,0,1,1,0,32.9V4.79A4.78,4.78,0,0,1,4.79,0H212.42a4.78,4.78,0,0,1,4.79,4.79V32.9A4.78,4.78,0,0,1,212.42,37.69Z"
                  />
                </g>
              </g>
            </svg>
          </a>
        </div>
        <div class="col-6 collapse-close">
          <close-button @click="closeMenu" :target="`navbar-${menu.type}`">
          </close-button>
        </div>
      </div>
      <component :is="menu.menuComponent"></component>
    </base-nav>
  </section>
</template>
<script>
import BaseNav from '@/components/BaseNav';
import CloseButton from '@/components/CloseButton';
import Menu1 from './Navigation/Menu1';
import Menu2 from './Navigation/Menu2';
import Menu3 from './Navigation/Menu3';
import Menu4 from './Navigation/Menu4';
import Menu5 from './Navigation/Menu5';
import Menu6 from './Navigation/Menu6';

export default {
  components: {
    BaseNav,
    CloseButton,
    Menu1,
    Menu2,
    Menu3,
    Menu4,
    Menu5,
    Menu6,
  },
  data() {
    return {
      menus: [
        { type: 'default', menuComponent: Menu1 },
        { type: 'primary', menuComponent: Menu2 },
        { type: 'success', menuComponent: Menu3 },
        { type: 'danger', menuComponent: Menu4 },
        { type: 'warning', menuComponent: Menu5 },
        { type: 'info', menuComponent: Menu6 },
      ],
    };
  },
};
</script>
<style>
</style>
