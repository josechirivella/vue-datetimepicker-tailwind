<template>
  <div id="hello-world-container">
    <div class="d-inline-flex align-items-center">
      <div class="mr-5">
        <label for="example-datepicker">Choose a date</label>
        <b-form-datepicker
          id="example-datepicker"
          v-model="value"
          class="mb-2"
        ></b-form-datepicker>
        Value: {{ value }}
      </div>
      <div>
        <b-time v-model="timeValue" locale="en" @context="onContext"></b-time>
        <p>Value: '{{ timeValue }}'</p>
      </div>
    </div>
  </div>
</template>

<script>
import { BFormDatepicker, BTime } from "bootstrap-vue";

export default {
  components: {
    BFormDatepicker,
    BTime,
  },
  data() {
    return {
      value: "",
      timeValue: "",
      context: null,
    };
  },
  methods: {
    onContext(ctx) {
      this.context = ctx;
    },
  },
};
</script>

<style lang="scss">
#hello-world-container {
  width: 50%;
  margin: 0 auto;
}
</style>
