<template>
  <h1>Form Wizard</h1>

  <Contact v-if="step === 1"/>
  <Shipping v-else-if="step === 2"/>
  <Review v-else/>

  <Button label="Previous" v-if="step > 1" @click="step -= 1"/>
  <Button label="Next" v-if="step < 3" @click="step += 1"/>
  <Button label="Submit" v-else @click="submit"/>
</template>

<script>
import Button from 'primevue/button';

import Contact from '@/components/Contact.vue';
import Shipping from '@/components/Shipping.vue';
import Review from '@/components/Review.vue';


export default {
  name: 'App',
  components: {
    Button,
    Contact,
    Shipping,
    Review
  },
  data () {
    return {
      step: 1
    }
  }
}
</script>

<style>
</style>
