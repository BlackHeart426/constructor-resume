<template>
  <div class="card card-w70">
    <h3 v-if="content.length === 0">Добавьте первый блок, чтобы увидеть результат</h3>

    <component v-for="(item, idx) of content" :is=item.nameComponent :key="idx" :value=item.value></component>

  </div>
</template>

<script>
import AppTitle from "@/components/AppTitle";
import AppAvatar from "@/components/AppAvatar";
import AppSubtitle from "@/components/AppSubtitle";
import AppText from "@/components/AppText";

export default {
  props: [
      'content'
  ],
  components: {
    AppTitle,
    AppAvatar,
    AppSubtitle,
    AppText,
  },
  name: "AppContent",
}
</script>

<style scoped>

</style>