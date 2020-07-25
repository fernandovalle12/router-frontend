<template>
  <v-container fluid>
    <v-row class="text-center">
      <v-col cols="12" sm="12" md="6">
        <v-form ref="form" v-model="valid" :lazy-validation="lazy">
          <v-text-field
            v-model="url"
            :rules="urlRules"
            label="URL"
            placeholder="Enter your URL"
            required
            outlined
          ></v-text-field>
          <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">Send</v-btn>
          <v-btn color="error" class="mr-4" @click="reset">Reset</v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",

  data: () => ({
    valid: true,
    url: "",
    urlRules: [v => !!v || "URL is required"]
  }),
  methods: {
    validate() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    },
    resetValidation() {
      this.$refs.form.resetValidation();
    }
  }
};
</script>
