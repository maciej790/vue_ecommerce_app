<template>
  <nav class="navigate">
    <div class="navigate__logo">
      <i class="fas fa-store-alt fa-2x"></i>
    </div>
    <button class="navigate__button" @click="isNavOpen = !isNavOpen">
      <i class="fas fa-ellipsis-h fa-2x"></i>
    </button>
    <ul :class="['navigate__options', { open: isNavOpen }]">
      <li
        class="navigate__options--item"
        v-for="(item, index) in menuItems"
        :key="index"
        @click="isNavOpen = !isNavOpen"
      >
        {{ item }}
      </li>
    </ul>
    <div class="navigate__cart">
      <i class="fas fa-shopping-cart fa-2x"></i>
    </div>
  </nav>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'TopNavigate',

  setup() {
    const menuItems = ['electronics', 'jewelery', "men's clothing", "women's clothing"];
    const isNavOpen = ref(false);

    return {
      menuItems,
      isNavOpen,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../style/TopNavigate.scss";
</style>
