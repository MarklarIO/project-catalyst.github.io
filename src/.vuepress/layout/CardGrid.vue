<template>
  <v-container fluid>
    <template v-for="row in gridRowCount">
      <v-row dense>
        <template v-for="col in gridColCount">
          <v-col v-if="this.cardIdx(row, col) < this.filteredCards.length">
            <ResourceCard
              v-bind:title="this.filteredCardsg[this.cardIdx(row, col)].title",
              v-bind:subtitle="this.filteredCardsg[this.cardIdx(row, col)].subtitle",
              v-bind:linkurl="this.filteredCardsg[this.cardIdx(row, col)].linkurl",
              v-bind:cardcolor="this.filteredCardsg[this.cardIdx(row, col)].cardcolor",
              v-bind:text="this.filteredCardsg[this.cardIdx(row, col)].text"
            />
          </v-col>
        </template>
      </v-row>
    </template>
  </v-container>
</template>

<script>
export default {
  props: {
    cards: {
      type: object
      required: true
    }
  },
  computed: {
    // TODO: Add hook to filter cards out.
    filteredCards () {
      return this.cards.filter(function (card) {
        return true;
      })
    },

    // Derive Grid Width from Container Width.
    gridColCount () {
      // TODO: dynamically fetch the width
      console.log(this.width)
      return Math.floor(this.width / 400);
    },

    // Derive Number of Rows.
    gridRowCount () {
      return Math.ceil(this.filteredCards.length / this.gridColCount);
    },

  }
  methods: {
    cardIdx: function(row, col) {
      return (row - 1) * this.gridColCount + col;
    }
  }
}
console.log(this.filteredCards)
console.log(this.gridColCount)
console.log(this.gridRowCount)
</script>
