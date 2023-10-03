<template>
  <v-form class="contact-form" ref="form" v-model="valid" @submit.prevent="sendMail">
    <v-text-field
        class="contact-text"
        v-model="name"
        :rules="nameRules"
        label="Name"
        required
    ></v-text-field>
    <v-text-field
        class="contact-text"
        v-model="email"
        :rules="emailRules"
        label="E-mail"
        required
    ></v-text-field>
    <v-textarea
        class="contact-text"
        v-model="message"
        :rules="messageRules"
        label="Message"
        required
    ></v-textarea>
    <v-btn
        class="contact-text"
        :disabled="!valid"
        type="submit"
    >
      Send Message
    </v-btn>
  </v-form>
</template>

<script>

export default {
  name: 'contactMe',

  components: {
  },

  data: () => ({
    valid: true,
    name: '',
    email: '',
    message: '',
    nameRules: [
      v => !!v || 'Name is required',
    ],
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],
    messageRules: [
      v => !!v || 'Message is required',
    ],
  }),
  methods: {
    sendMail() {
      if (this.$refs.form.validate()) {
        const mailtoLink = `mailto:kcanakdag26@gmail.com?subject=Message from ${this.name} (${this.email})&body=${encodeURIComponent(this.message)}`;
        window.location.href = mailtoLink;
      }
    },
  },
}
</script>


<style scoped>
.contact-form{
  width: 50vw;
}

.contact-text{
  color: #45B1A0;
}
</style>
