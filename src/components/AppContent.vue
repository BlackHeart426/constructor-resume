<template>
  <div class="card card-w70">
    <h3 v-if="content.length === 0">Добавьте первый блок, чтобы увидеть результат</h3>
    <app-title/>
    <app-avatar/>
    <app-subtitle/>
    <app-text/>
    <component v-for="(item, idx) of content" :is="item" :key="idx" :value="item.value"></component>
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
      content: [
        {
          nameComponent: 'app-title',
          value: '12312'
        },
        {
          nameComponent: 'app-avatar',
          value: '12312'
        },
        {
          nameComponent: 'app-subtitle',
          value: '12312'
        },
      ],

    }
  },
}
</script>

<style scoped>

</style>