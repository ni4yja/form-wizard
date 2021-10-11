<template>
  <h2>Contact</h2>
  <div>
    <InputText type="text" v-model="value" />
    <InputText type="text" v-model="value" />
    <InputText type="text" v-model="value" />
  </div>
</template>

<script>
import InputText from 'primevue/inputtext';

export default {
  components: {
    InputText,
  }
}
</script>

<style>

</style>