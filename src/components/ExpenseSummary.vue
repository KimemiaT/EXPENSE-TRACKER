<template>
  <div class="summary">
    <h2>Total Expenses: ${{ total }}</h2>
  </div>
</template>

<script>
export default {
  props: ["expenses"],
  computed: {
    total() {
      return this.expenses.reduce((sum, expense) => sum + expense.amount, 0);
    },
  },
};
</script>

<style scoped>
.summary {
  font-size: 1.5em;
  font-weight: bold;
}
</style>
