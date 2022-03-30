<template v-slot:default>
  <v-simple-table>
    <thead>
      <tr>
        <th class="text-left">Index</th>
        <th class="text-left">Word</th>
        <th class="text-left">Result</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in items" :key="item.word">
        <td>{{ item.index }}</td>
        <td>{{ item.word }}</td>
        <td :class="cellColour[item.result]">{{ item.result }}</td>
      </tr>
    </tbody>
  </v-simple-table>
</template>

<script>
export default {
  data() {
    return {
      cellColour: {
        YES: "isPalindromeCell",
        NO: "isNotPalindromeCell",
      },
      items: [
        { index: 1, word: "anna", result: "" },
        { index: 2, word: "Anna", result: "" },
        { index: 3, word: "anna ", result: "" },
        { index: 4, word: "Yellowsubmarine", result: "" },
      ],
    };
  },

  methods: {
    checkIfPalindrome() {
      for (let i = 0; i < this.items.length; i++) {
        const itemsData = this.items[i];
        let wordToCheck = itemsData.word;
        let wordWithoutSpaces = wordToCheck.replace(/\s+/g, " ").trim();
        let lowerCase = wordWithoutSpaces.toLowerCase();
        let reversed = lowerCase.split("").reverse().join("");
        if (lowerCase === reversed) {
          itemsData.result = "YES";
        } else {
          itemsData.result = "NO";
        }
      }
    },
  },
  mounted() {
    this.checkIfPalindrome();
  },
};
</script>
<style>
.isPalindromeCell {
  background-color: #28f00e;
}

.isNotPalindromeCell {
  background-color: #f02020;
}
</style>
