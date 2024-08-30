/*
 * author: lijx
 * date: 2024-08-28
 * fileName: ExerciseView.vue
 * description:
*/

<script setup lang="ts">
  import { ref, onMounted } from 'vue'
  import { message, Button, Input } from 'ant-design-vue'
  // import {  } from '@/services'
  const people = ref({
    name:'张三',
    age:18,
    tel:'13888888888'
  })
  const size = 'small'
  const handleNameChange = () => {
    people.value.name = '李四'
    message.success('修改成功')
  }
  const handleAgeAdd = () => {
    people.value.age += 1
    message.success('年龄+1')
  }
  const handleTelChange = () => {
    people.value.tel = '13999999999'
    message.success('修改成功')
  }
</script>

<template>
  <div>
    <h1>ExerciseView People</h1>
    <div>姓名：{{ people.name }} <Button :size="size" @click="handleNameChange">修改名字</Button></div>
    <div>年龄：{{ people.age }} <Button :size="size" @click="handleAgeAdd">年龄+1</Button></div>
    <div>电话：{{ people.tel }} <Button :size="size" @click="handleTelChange">修改名字</Button></div>
  </div>
</template>