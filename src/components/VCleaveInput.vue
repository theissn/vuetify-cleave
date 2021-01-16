<script>
import Cleave from "cleave.js";

export default {
  props: ["value", "options"],
  data() {
    return {
      local: this.value,
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
  beforeUpdate() {
    this.cleave.setRawValue(this.value);
  },
  methods: {
    onValueChanged({ target }) {
        this.local = target.value;
        this.$emit("input", target.rawValue);
    }
  }
};
</script>

<template>
  <v-text-field :value="local" v-bind="$attrs" />
</template>
