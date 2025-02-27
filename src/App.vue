<template>
  <div class="app-container">
    <h1 class="title">💰 Expense Tracker</h1>

    <!-- Expense Input Form -->
    <div class="input-container">
      <input v-model="newExpense.category" placeholder="Category" class="input-field" />
      <input v-model.number="newExpense.amount" type="number" placeholder="Amount" class="input-field" />
      <button @click="addExpense" class="add-btn">➕ Add Expense</button>
    </div>

    <!-- Expenses List -->
    <ExpenseList :expenses="expenses" @remove-expense="removeExpense" />

    <!-- Expense Chart -->
    <ExpenseChart :expenses="expenses" />
  </div>
</template>

<script>
import { ref } from "vue";
import ExpenseList from "./components/ExpenseList.vue";
import ExpenseChart from "./components/ExpenseChart.vue";

export default {
  components: { ExpenseList, ExpenseChart },
  setup() {
    const expenses = ref([]); // Reactive expense list
    const newExpense = ref({ category: "", amount: null });

    // ✅ Fix: Add Expense Correctly
    const addExpense = () => {
      if (newExpense.value.category && newExpense.value.amount) {
        expenses.value = [...expenses.value, { ...newExpense.value }];
        newExpense.value = { category: "", amount: null }; // Reset input fields
      }
    };

    // ✅ Fix: Remove Expense
    const removeExpense = (index) => {
      expenses.value = expenses.value.filter((_, i) => i !== index);
    };

    return { expenses, newExpense, addExpense, removeExpense };
  },
};
</script>

<style scoped>
.app-container {
  max-width: 600px;
  margin: auto;
  padding: 20px;
  background: #1e1e2f;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  color: white;
}

.title {
  text-align: center;
  font-size: 1.5rem;
  margin-bottom: 15px;
}

.input-container {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.input-field {
  flex: 1;
  padding: 8px;
  border-radius: 6px;
  border: none;
  font-size: 1rem;
}

.add-btn {
  background: #8b5cf6;
  color: white;
  border: none;
  padding: 8px 12px;
  border-radius: 6px;
  cursor: pointer;
}

.add-btn:hover {
  background: #6d28d9;
}
</style>
