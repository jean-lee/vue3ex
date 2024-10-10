/*
 * author: lijx
 * date: 2024-08-28
 * fileName: ExerciseView.vue
 * description:
*/

<script setup lang="ts">
  import { ref, onMounted } from 'vue'
  import { message, Button, Input } from 'ant-design-vue'

  const person = ref({
    name: '张三',
    age: 18,
    tel: '13888888888'
  })
  const size = 'small'
  const handleNameChange = () => {
    person.value.name = `李四 ${(Math.random(1,100) * 1000).toFixed(3)}`
    message.success('修改成功')
  }
  const handleAgeAdd = () => {
    person.value.age += 1
    message.success('年龄+1')
  }
  const handleTelChange = () => {
    person.value.tel = (Math.random(1,100) * 100000000000).toFixed(0)
    message.success('修改成功')
  }
</script>

<template>
  <div>
    <h1>ExerciseView A1</h1>
    <div>姓名：{{ person.name }} <Button :size="size" @click="handleNameChange">修改名字</Button></div>
    <div>年龄：{{ person.age }} <Button :size="size" @click="handleAgeAdd">年龄+1</Button></div>
    <div>电话：{{ person.tel }} <Button :size="size" @click="handleTelChange">修改手机号</Button></div>
  </div>
</template>

<style scoped>
  div {
    margin-top: 10px;
  }
  button {
    margin-left: 10px;
  }
</style>