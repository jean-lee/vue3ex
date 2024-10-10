/*
 * author: lijx
 * date: 2024-09-03
 * fileName: ExerciseView.vue
 * description: 练习汇总
 */

<script setup lang="ts">
  import { ref, onMounted } from 'vue'
  import { message, Button, Input } from 'ant-design-vue'
  import { RouterLink, RouterView, useRoute, useRouter } from 'vue-router'

  const route = useRoute()
  const router = useRouter()
  const active = ref('/exercise/A1')

  const goPath = (str) => {
    active.value = str
    router.push({ path: str })
    console.log('goPath', str)
  }
</script>

<template>
  <div>
    <h3 style="font-weight: bold;">练习汇总</h3>
    <!-- <nav>
      <RouterLink to="/exercise/A1">A1</RouterLink>
      <RouterLink to="/exercise/A2">A2</RouterLink>
    </nav> -->
    <ul>
      <li @click="goPath('/exercise/A1')" :class="'/exercise/A1' === active ? 'active' : ''">A1</li>
      <li @click="goPath('/exercise/A2')" :class="'/exercise/A2' === active ? 'active' : ''">A2</li>
    </ul>

    <RouterView />
  </div>
</template>

<style scoped>
  ul {
    list-style: cjk-ideographic;
  }
  li {
    cursor: pointer;
    /* padding: 10px; */
    /* border: 1px solid #ccc; */
    text-decoration: underline;
    &:hover {
      color: red;
    }
  }
  li.active {
    color: red;
    font-weight: bold;
  }
</style>