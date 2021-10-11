<template>
  <div class="p-grid">
    <div class="p-col-4 p-offset-4">
      <h1>Form Wizard</h1>
      <Card>
        <template #title> {{ stepTitle }}</template>
        <template #content>
          <Contact v-if="step === 1" />
          <Shipping v-else-if="step === 2" />
          <Review v-else />
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
    };
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
  }
};
</script>

<style>
input {
  width: 100%;
}
</style>
