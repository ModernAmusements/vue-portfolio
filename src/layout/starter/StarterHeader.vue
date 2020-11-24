<template>
  <header class="header-global">
    <base-nav class="navbar-main" transparent type="" effect="light" expand>
      <router-link slot="brand" class="navbar-brand mr-lg-5" to="/">
        <img src="img/brand/white.png" />
      </router-link>

      <div class="row" slot="content-header" slot-scope="{ closeMenu }">
        <div class="col-6 collapse-brand">
          <a href="../index.html">
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
          <close-button @click="closeMenu"></close-button>
        </div>
      </div>

      <ul class="navbar-nav navbar-nav-hover align-items-lg-center">
        <li class="nav-item dropdown">
          <a href="#" class="nav-link" data-toggle="dropdown" role="button">
            <i class="ni ni-ui-04 d-lg-none"></i>
            <span class="nav-link-inner--text">Components</span>
          </a>
          <div class="dropdown-menu dropdown-menu-xl">
            <div class="dropdown-menu-inner">
              <a
                href="https://demos.creative-tim.com/argon-design-system/docs/getting-started/overview.html"
                class="media d-flex align-items-center"
              >
                <div
                  class="icon icon-shape bg-gradient-primary rounded-circle text-white"
                >
                  <i class="ni ni-spaceship"></i>
                </div>
                <div class="media-body ml-3">
                  <h6 class="heading text-primary mb-md-1">Getting started</h6>
                  <p class="description d-none d-md-inline-block mb-0">
                    Get started with Bootstrap, the world's most popular
                    framework for building responsive sites.
                  </p>
                </div>
              </a>
              <a
                href="https://demos.creative-tim.com/argon-design-system/docs/components/alerts.html"
                class="media d-flex align-items-center"
              >
                <div
                  class="icon icon-shape bg-gradient-warning rounded-circle text-white"
                >
                  <i class="ni ni-ui-04"></i>
                </div>
                <div class="media-body ml-3">
                  <h5 class="heading text-warning mb-md-1">Components</h5>
                  <p class="description d-none d-md-inline-block mb-0">
                    Learn how to use Argon compiling Scss, change brand colors
                    and more.
                  </p>
                </div>
              </a>
            </div>
          </div>
        </li>
        <li class="nav-item dropdown">
          <a href="#" class="nav-link" data-toggle="dropdown" role="button">
            <i class="ni ni-collection d-lg-none"></i>
            <span class="nav-link-inner--text">Examples</span>
          </a>
          <div class="dropdown-menu">
            <router-link to="/landing" class="dropdown-item"
              >Landing</router-link
            >
            <router-link to="/profile" class="dropdown-item"
              >Profile</router-link
            >
            <router-link to="/login" class="dropdown-item">Login</router-link>
            <router-link to="/register" class="dropdown-item"
              >Register</router-link
            >
          </div>
        </li>
      </ul>
      <ul class="navbar-nav align-items-lg-center ml-lg-auto">
        <li class="nav-item">
          <a
            class="nav-link nav-link-icon"
            href="https://www.facebook.com/creativetim"
            target="_blank"
            data-toggle="tooltip"
            title="Like us on Facebook"
          >
            <i class="fa fa-facebook-square"></i>
            <span class="nav-link-inner--text d-lg-none">Facebook</span>
          </a>
        </li>
        <li class="nav-item">
          <a
            class="nav-link nav-link-icon"
            href="https://www.instagram.com/creativetimofficial"
            target="_blank"
            data-toggle="tooltip"
            title="Follow us on Instagram"
          >
            <i class="fa fa-instagram"></i>
            <span class="nav-link-inner--text d-lg-none">Instagram</span>
          </a>
        </li>
        <li class="nav-item">
          <a
            class="nav-link nav-link-icon"
            href="https://twitter.com/creativetim"
            target="_blank"
            data-toggle="tooltip"
            title="Follow us on Twitter"
          >
            <i class="fa fa-twitter-square"></i>
            <span class="nav-link-inner--text d-lg-none">Twitter</span>
          </a>
        </li>
        <li class="nav-item">
          <a
            class="nav-link nav-link-icon"
            href="https://github.com/creativetimofficial/vue-argon-design-system"
            target="_blank"
            data-toggle="tooltip"
            title="Star us on Github"
          >
            <i class="fa fa-github"></i>
            <span class="nav-link-inner--text d-lg-none">Github</span>
          </a>
        </li>
        <li class="nav-item d-none d-lg-block ml-lg-4">
          <a
            href="https://www.creative-tim.com/product/vue-argon-design-system"
            target="_blank"
            class="btn btn-neutral btn-icon"
          >
            <span class="btn-inner--icon">
              <i class="fa fa-cloud-download mr-2"></i>
            </span>
            <span class="nav-link-inner--text">Download</span>
          </a>
        </li>
      </ul>
    </base-nav>
  </header>
</template>
<script>
import BaseNav from '@/components/BaseNav';
import CloseButton from '@/components/CloseButton';

export default {
  components: {
    BaseNav,
    CloseButton,
  },
};
</script>
<style>
</style>
