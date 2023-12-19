<template>
  <div :class="store.mobileOpenState ? 'left hidden' : 'left'">
    <Logo />
    <Search />
    <Msg />
    <SocialLinks />
  </div>
</template>

<script setup>
import { mainStore } from "@/store";
import SocialLinks from "@/components/SocialLinks.vue";
import Logo from "@/components/Logo.vue";
import Msg from "@/components/Msg.vue";
import Search from "@/components/Search.vue";
const store = mainStore();
</script>

<style lang="scss" scoped>
.left {
  // flex: 1 0 0%;
  width: 50%;
  margin-right: 10px;
  transform: translateY(20px);
  &.hidden {
    display: none;
  }
  @media (max-width: 720px) {
    margin-right: 0;
    width: 100%;
  }
}
</style>
