<template>
  <div class="p-grid">
    <div class="p-col-4 p-offset-4">
      <h1>Form Wizard</h1>
      <Card>
        <template #title> {{ stepTitle }}</template>
        <template #content>
          <Contact 
            v-if="step === 1"
            v-model:name="contactInfo.name"
            v-model:email="contactInfo.email"
            v-model:phone="contactInfo.phone" 
          />
          <Shipping 
            v-else-if="step === 2"
            v-model:street="shippingInfo.street"
            v-model:state="shippingInfo.state"
            v-model:zip="shippingInfo.zip" 
          />
          <Review 
            v-else
            :contactInfo="contactInfo"
            :shippingInfo="shippingInfo"
          />
        </template>
        <template #footer>
          <Button label="Previous" v-if="step > 1" @click="step -= 1" />
          <Button label="Next" v-if="step < 3" @click="step += 1" />
          <Button label="Submit" v-else @click="submit" />
        </template>
      </Card>
    </div>
  </div>
</template>

<script>
import Button from "primevue/button";
import Card from "primevue/card";

import Contact from "@/components/Contact.vue";
import Shipping from "@/components/Shipping.vue";
import Review from "@/components/Review.vue";

export default {
  name: "App",
  components: {
    Button,
    Card,
    Contact,
    Shipping,
    Review,
  },
  data() {
    return {
      step: 1,
      contactInfo: {
        name: '',
        email: '',
        phone: ''
      },
      shippingInfo: {
        street: '',
        state: '',
        zip: null
      }
    }
  },
  computed: {
    stepTitle () {
      if (this.step === 1) {
        return 'Contact'
      } else if (this.step === 2) {
        return 'Shipping'
      } else {
        return 'Review'
      }
    }
  },
  methods: {
    submit () {
      console.log("The form is submitted")
    }
  }
};
</script>

<style>
input {
  width: 100%;
}
</style>
