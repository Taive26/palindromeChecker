<template>
  <div class="mx-auto">
    <b-form>
      <b-form-input
        id="input-1"
        v-model="form.word"
        placeholder="Enter a word and see if it's a palindrome"
        required
      ></b-form-input>

      <h1>{{ answer }}</h1>

      <b-button type="submit" variant="primary" @click="checkIfPalindrome()"
        >Submit</b-button
      >
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      answer: "",
      form: {
        word: "",
      },
    };
  },
  methods: {
    checkIfPalindrome() {
      console.log(this.form.word);
      let wordToCheck = this.form.word;
      let wordWithoutSpaces = wordToCheck.replace(/\s+/g, " ").trim();
      let lowerCase = wordWithoutSpaces.toLowerCase();
      let reversed = lowerCase.split("").reverse().join("");
      if (lowerCase === reversed) {
        this.answer = "YES";
      } else {
        this.answer = "NO";
      }
      console.log(this.answer);
    },
  },
};
</script>
