<template>
  <div class="card card-w70">
    <h3 v-if="content.length === 0">Добавьте первый блок, чтобы увидеть результат</h3>
    <app-title/>
    <app-avatar/>
    <app-subtitle/>
    <app-text/>
  </div>
</template>

<script>
import AppTitle from "@/components/AppTitle";
import AppAvatar from "@/components/AppAvatar";
import AppSubtitle from "@/components/AppSubtitle";
import AppText from "@/components/AppText";

export default {
  components: {
    AppTitle,
    AppAvatar,
    AppSubtitle,
    AppText,
  },
  name: "AppContent",
  data() {
    return {
      content: [],

    }
  },
}
</script>

<style scoped>

</style>