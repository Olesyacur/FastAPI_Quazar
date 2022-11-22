<template>
  <div class="row">
    <div class="offset-2 col-8 q-mt-xl">
      <div>
        Я, {{ name }} {{ cur_dt }},обещаю бросить курить в 45 лет.
        <br>
        _______________/{{ name }}/
      </div>
      <div style="margin-top: 20px;">
      <q-input class="name-input" v-model="name"></q-input>
      <br>
      <q-btn>
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
</script>

<style lang="scss">
.name-input {
  max-width: 300px
}
</style>