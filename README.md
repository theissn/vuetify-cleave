# vuetify-cleave

# Demo

https://vuetify-cleave.netlify.com/

# Installation
```
# npm
npm install vuetify-cleave

# Yarn
yarn add vuetify-cleave
```

# Usage

View all possible props on [vuetify's docs](https://vuetifyjs.com/en/components/text-fields#api)

```
<template>
  <VCleaveInput
    v-model="cardNumber"
    :options="creditCard"
    placeholder="Credit card"
  />
</template>
<script>
import VCleaveInput from "vuetify-cleave";

export default {
  name: 'App',
  components: {
    VCleaveInput
  },
  data() {
    return {
      cardNumber: null,
      creditCard: {
        creditCard: true,
        delimiter: " "
      },
    };
  }
};
</script>
```

For other uses see examples: https://github.com/theissn/vuetify-cleave/blob/master/src/App.vue