<template>
  <h1>Form Wizard</h1>
  
  <Contact />
  <Shipping />
  <Review />
</template>

<script>

import Contact from '@/components/Contact.vue';
import Shipping from '@/components/Shipping.vue';
import Review from '@/components/Review.vue';


export default {
  name: 'App',
  components: {
    Contact,
    Shipping,
    Review
  }
}
</script>

<style>
</style>
