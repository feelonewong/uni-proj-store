<template>
    <uni-nav-bar 
      :fixed="true" 
      :status-bar="true" 
      :border="false" 
      background-color="#f3f3f3"
      left-width="0"
      right-width="0"
      >
      <Search color="999999" background-color="#f6f6f6"></Search>
    </uni-nav-bar>
</template>

<script setup lang="ts">
import Search from "@/components/Search.vue"
</script>

<style lang="scss" scoped>

</style>