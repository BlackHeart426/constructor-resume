<template>
  <div class="container column">
    <app-menu/>
    <app-content/>
  </div>
  <app-comment/>
</template>

<script>
import AppComment from "@/components/AppComment";
import AppContent from "@/components/AppContent";
import AppMenu from "@/components/AppMenu";

export default {
  components: {
    AppComment,
    AppContent,
    AppMenu,
  }
}
</script>

<style>

</style>
