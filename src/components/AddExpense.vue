<template>
    <div class="expense-form">
      <h2>Add Expense</h2>
      <input v-model="name" type="text" placeholder="Expense Name" />
      <input v-model.number="amount" type="number" placeholder="Amount" />
      <select v-model="category">
        <option value="Food">Food</option>
        <option value="Transport">Transport</option>
        <option value="Entertainment">Entertainment</option>
        <option value="Rent">Rent</option>

      </select>
      <button @click="addExpense">Add</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: "",
        amount: "",
        category: "Food",
      };
    },
    methods: {
      addExpense() {
        if (!this.name || !this.amount) return;
        this.$emit("expense-added", {
          name: this.name,
          amount: this.amount,
          category: this.category,
          id: Date.now(),
        });
        this.name = "";
        this.amount = "";
      },
    },
  };
  </script>
  
  <style scoped>
  .expense-form {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  </style>
  