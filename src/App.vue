<template>
  <div id="app">
    <v-container>
      <v-row>
        <v-col cols="12" md="4" offset-md="4">
          <div class="display-1">Credit Card</div>
          <VCleaveInput
            v-model="form.cardNumber"
            :options="options.creditCard"
            placeholder="Credit card"
          />
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="4" offset-md="4">
          <div class="display-1">Date (DD/MM/YYYY)</div>
          <VCleaveInput
            v-model="form.date"
            :options="options.date"
            placeholder="Date"
          />
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="4" offset-md="4">
          <div class="display-1">Currency / Amount</div>
          <VCleaveInput
            v-model="form.number"
            :options="options.number"
            placeholder="Money"
          />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import VCleaveInput from "./components/VCleaveInput.vue";

export default {
  components: {
    VCleaveInput
  },
  data() {
    return {
      cardType: null,
      form: {
        cardNumber: null,
        date: null,
        number: null
      },
      options: {
        creditCard: {
          creditCard: true,
          delimiter: " "
        },
        date: {
          date: true,
          datePattern: ["d", "m", "Y"],
          delimiter: "/"
        },
        number: {
          prefix: "$ ",
          numeral: true,
          numeralPositiveOnly: true,
          noImmediatePrefix: true,
          rawValueTrimPrefix: true,
          numeralIntegerScale: 9,
          numeralDecimalScale: 2
        }
      }
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
