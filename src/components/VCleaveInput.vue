<script>
import Cleave from "cleave.js";

export default {
  props: {
    options: {
      type: Object,
      default: null
    }
  },
  data() {
    return {
      value: null,
      attrs: ["outlined", "rounded"]
    };
  },
  mounted() {
    this.cleave = new Cleave(this.$el.querySelector("input"), {
      ...this.options,
      onValueChanged: this.onValueChanged.bind(this)
    });

    this.cleave.setRawValue(this.value);
  },
  methods: {
    onValueChanged({ target }) {
      this.$nextTick(() => {
        this.value = target.value;
        this.$emit("input", target.rawValue);
      });
    }
  }
};
</script>

<template>
  <v-text-field v-model="value" v-bind="$attrs" />
</template>
