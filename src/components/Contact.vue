<template>
  <div class="p-field">
    <label for="name-input">Name</label>
    <InputText id="name-input" :value="name" @input="changeName" type="text"/>
  </div>
  <div class="p-field">
    <label for="email-input">E-mail</label>
    <InputText id="email-input" :value="email" @input="changeEmail" type="email"/>
  </div>
  <div class="p-field">
    <label for="phone-input">Phone</label>
    <InputText id="phone-input" :value="phone" @input="changePhone" type="tel"/>
  </div>
</template>

<script>
import InputText from 'primevue/inputtext';

export default {
  components: {
    InputText,
  },
  props: {
    name: String,
    email: String,
    phone: String
  },
  emits: [
    'update:name',
    'update:email',
    'update:phone'
  ],
  methods: {
    changeName (e) {
      this.$emit('update:name', e.target.value)
    },
    changeEmail (e) {
      this.$emit('update:email', e.target.value)
    },
    changePhone (e) {
      this.$emit('update:phone', e.target.value)
    }
  }
}
</script>

<style>

</style>