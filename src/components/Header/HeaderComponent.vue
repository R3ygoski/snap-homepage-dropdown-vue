<script setup>
import { ref, onMounted } from 'vue';
import FeatureDropdown from './FeatureDropdown.vue';
import CompanyDropdown from './CompanyDropdown.vue';

let windowWidth = ref(window.innerWidth)
let isMenuOpen = ref(false)
let isDesktop = ref(false)

const updateWindow = () => {
  windowWidth.value = window.innerWidth
  if (windowWidth.value >= 1024) {
    isDesktop.value = true
  } else {
    isDesktop.value = false
  }
}

const toggleSidebar = () => {
  isMenuOpen.value = !isMenuOpen.value
}

onMounted(() => {
  updateWindow()
  window.addEventListener('resize', updateWindow)
})

</script>

<template>
  <header class="header">
    <img class="header__logo" src="../../assets/images/logo.svg" alt="Snap Logo" />
    <nav :class="isMenuOpen || isDesktop ? 'header__navbar move-left' : 'header__navbar--hidden'">

      <ul class="header__navbar-list">
        <!-- Features -->
        <FeatureDropdown />
        <!-- Company -->
        <CompanyDropdown />
        <!-- Others -->
        <li class="header__navbar-list-item">
          <a href="#">Careers</a>
        </li>
        <li class="header__navbar-list-item">
          <a href="#">About</a>
        </li>
        <!-- Login & Register -->
        <li class="header__navbar-auth">
            <ul class="header__navbar-auth__container">
              <li class="header__navbar-auth__container-login">
                <a href="#">Login</a>
              </li>
              <li class="header__navbar-auth__container-sign-up">
                <a href="#">Register</a>
              </li>
            </ul>
        </li>
      </ul>

    </nav>
    <button v-if="!isDesktop" :class="isDesktop ? 'hidden' : 'header__navbar-btn'" type="button" @:click="toggleSidebar">
      <img v-if="isMenuOpen == false" src="../../assets/icon/icon-menu.svg" alt="Menu" />
      <img v-else class="close-menu" src="../../assets/icon/icon-close-menu.svg" alt="Close Menu" />
    </button>
  </header>
</template>