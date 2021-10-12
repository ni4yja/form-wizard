<template>
  <div class="p-field">
    <label for="street-input">Street</label>
    <InputText id="street-input" :value="street" @input="changeStreet" type="text"/>
  </div>
  <div class="p-field">
    <label for="state-input">State</label>
    <InputText id="state-input" :value="state" @input="changeState" type="email"/>
  </div>
  <div class="p-field">
    <label for="zip-input">Zip</label>
    <InputText id="zip-input" :value="zip" @input="changeZip" type="number"/>
  </div>
</template>

<script>
import InputText from 'primevue/inputtext';

export default {
  components: {
    InputText,
  },
  props: {
    street: String,
    state: String,
    zip: Number
  },
  emits: [
    'update:street',
    'update:state',
    'update:zip'
  ],
  methods: {
    changeStreet (e) {
      this.$emit('update:street', e.target.value)
    },
    changeState (e) {
      this.$emit('update:state', e.target.value)
    },
    changeZip (e) {
      this.$emit('update:zip', parseInt(e.target.value))
    }
  }
}
</script>

<style>

</style>