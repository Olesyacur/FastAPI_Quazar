<template>
  <div class="row">
    <div class="offset-2 col-8 q-mt-xl">
      <div>
        Я, {{ name }} {{ cur_dt }},обещаю выучить Python.
        <br>
        _______________/{{ name }}/
      </div>
      <div style="margin-top: 20px;">
      <q-input
        rules:="[v => !!v || 'Пожалуйста, введите имя']"
        class="name-input"
        v-model="name"
      ></q-input>
      <br>
      <q-btn>
        @click="getCurTime"
        Установить имя
      </q-btn>
      </div>
    </div>
  </div>
</template>

<script setup>
import { api } from 'src/boot/axios'
import { ref } from 'vue'

const cur_dt = ref('')
const name = ref('')

function getCurTime() {
  api.post('/api/get_cur_dt')
  .then(ans => {
    cur_dt.value = ans.data.cur_dt
  })
}
</script>

<style lang="scss">
.name-input {
  max-width: 300px
}
</style>