<script setup>
import { ref } from 'vue'

const input_weight = ref(0)
const input_height = ref(0)
const result = ref(0)

function cal_bmi() {
  const heightInMeters = input_height.value / 100
  result.value = input_weight.value / (heightInMeters * heightInMeters)
}

function clear() {
  input_weight.value = 0
  input_height.value = 0
  result.value = 0
}
</script>

<template>
  <h2>โปรแกรม KK BMI 1.0</h2>
  <label>น้ำหนัก (kg)</label>
  <input type="number" placeholder="กรอกน้ำหนัก" v-model="input_weight" /><br /><br />
  <label>ส่วนสูง (cm)</label>
  <input type="number" placeholder="กรอกส่วนสูง" v-model="input_height" />
  <br /><br />
  <button @click="cal_bmi">คำนวณ</button>
  <button @click="clear">เคลียร์ค่า</button>
  <p>น้ำหนัก : {{ input_weight }}kg</p>
  <p>ส่วนสูง : {{ input_height }}cm</p>
  <p>BMI : {{ result }}</p>
</template>
