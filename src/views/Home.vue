<template>
  <b-container>
    <img alt="Vue logo" src="../assets/logo.png" />
    <b-card
      header="PALINDROME CHECKER"
      header-text-variant="black"
      header-bg-variant="info"
    >
      <b-card-body>
        <palindromeChecker />
      </b-card-body>
    </b-card>
    <insert-your-own-palindrome />
  </b-container>
</template>

<script>
import palindromeChecker from "@/components/palindromeChecker.vue";
import insertYourOwnPalindrome from "@/components/insertYourOwnPalindrome.vue";

export default {
  name: "Home",
  components: {
    palindromeChecker,
    insertYourOwnPalindrome,
  },
};
</script>
