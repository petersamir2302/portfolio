<template>
  <v-container grid-list-xl>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-4 mt-2">
          <span>GetIn</span>
          <span class="green--text">Touch</span>
        </h2>
        <a href="https://goo.gl/maps/BJRS2KFbTKMnrrUZ9" target="_blank">
          <div class="py-4 subheading font-weight-bold">
            <v-icon color="green" left>fas fa-map-marker-alt</v-icon>
            <div class="d-inline-flex text-dark m-auto">
              <span class="mt-n1">Cairo,&nbsp;</span>
              <span class="green--text">Egypt</span>
            </div>
          </div>
        </a>
        <a href="mailto:petersamirnazir@gmail.com" target="_blank">
          <div class="py-4 subheading font-weight-bold">
            <v-icon color="green" left>fas fa-envelope</v-icon>
            <div class="d-inline-flex text-dark m-auto">
              <span>petersamirnazir@</span>
              <span class="green--text">gmail.com</span>
            </div>
          </div>
        </a>
        <a href="tel:+201025652882" target="_blank">
          <div class="py-4 subheading font-weight-bold">
            <v-icon color="green" left>fas fa-phone</v-icon>
            <div class="d-inline-flex text-dark m-auto">
              <span>+2&nbsp;</span>
              <span class="green--text">01025652882</span>
            </div>
          </div>
        </a>
        <div class="py-4 subheading font-weight-bold">
          <v-icon color="green" left>fas fa-check</v-icon>
          <span>Freelance</span>
          <span class="green--text">Available</span>
        </div>
      </v-flex>

      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-4 mb-4">
          <span>Drop me a </span>
          <span class="green--text">Message</span>
        </h2>

        <form method="POST" action="https://formspree.io/f/mvojrjvy">
          <v-text-field name="name" color="green" background-color="transparent" v-model="name"
            :error-messages="nameErrors" label="Name" required @blur="$v.name.$touch()"></v-text-field>
          <v-text-field type="email" color="green" background-color="transparent" name="email" v-model="email"
            :error-messages="emailErrors" label="E-mail" required @blur="$v.email.$touch()"></v-text-field>
          <v-textarea color="green" background-color="transparent" :counter="200" :error-messages="bodyErrors"
            v-model="body" label="Message" name="body" @blur="$v.body.$touch()"></v-textarea>
          <v-btn @click="submit" type="submit" color="green" class="white--text" :disabled="(body.length <= 20)">SEND
            MESSAGE</v-btn>
          <v-btn @click="clear">clear</v-btn>
        </form>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import { validationMixin } from "vuelidate";
import {
  required,
  maxLength,
  email,
  minLength
} from "vuelidate/lib/validators";
export default {
  metaInfo: {
    title: "Contact",
    titleTemplate: "%s ← Peter's Space",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Peter Samir's Contact Doboj Bosnia and Herzegovina Freelance Get in Touch ContactMe"
      },
      { charset: "utf-8" },
      { property: "og:title", content: "Peter' Space" },
      { property: "og:site_name", content: "Peter' Space" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://peter.space" },
      {
        property: "og:image",
        content: "https://i.imgur.com/Dcz2PGx.jpg"
      },
      {
        property: "og:description",
        content:
          "Peter Samir's Contact Doboj Bosnia and Herzegovina Freelance Get in Touch ContactMe"
      }
    ]
  },
  mixins: [validationMixin],
  validations: {
    name: { required, maxLength: maxLength(20) },
    email: { required, email },
    body: { required, minLength: minLength(20) }
  },
  data() {
    return {
      name: "",
      email: "",
      body: ""
    };
  },
  methods: {
    submit() {
      this.$v.$touch();
    },
    clear() {
      this.$v.$reset();
      this.name = "";
      this.email = "";
      this.body = "";
    }
  },
  computed: {
    nameErrors() {
      const errors = [];
      if (!this.$v.name.$dirty) return errors;
      !this.$v.name.maxLength &&
        errors.push("Name must be at most 20 characters long");
      !this.$v.name.required && errors.push("Name is required.");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push("Must be valid e-mail");
      !this.$v.email.required && errors.push("E-mail is required");
      return errors;
    },
    bodyErrors() {
      const errors = [];
      if (!this.$v.body.$dirty) return errors;
      !this.$v.body.minLength &&
        errors.push("Text must be at least 20 characters long");
      !this.$v.body.required && errors.push("Text is required");
      return errors;
    }
  }
};
</script>

<style lang="scss" scoped></style>
