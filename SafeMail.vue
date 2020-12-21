<style lang="postcss" scoped>
a.safe-mail {
  unicode-bidi: bidi-override;
  direction: rtl;
}
</style>

<template>
  <a
    class="safe-mail"
    :href="'mailto:' + reversed"
    :title="title"
    @click="mailClicked"
    >{{ reversed }}</a
  >
</template>

<script>
export default {
  name: "SafeMail",
  props: {
    email: String,
    title: {
      type: String,
      default: null,
    },
  },
  data() {
    return {
      emailAlreadyClicked: false,
    };
  },
  computed: {
    reversed() {
      return this.email.split("").reverse().join("");
    },
  },
  methods: {
    mailClicked(e) {
      if (this.emailAlreadyClicked) return;
      // Lien déjà retourné donc comportement du lien par défaut
      else {
        e.preventDefault;
        this.emailAlreadyClicked = true;
        e.target.href = "mailto:" + this.email;
        console.log(e.target.href);
        e.target.click();
      }
    },
  },
};
</script>
