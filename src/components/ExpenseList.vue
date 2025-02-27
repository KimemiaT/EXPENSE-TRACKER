<template>
  <div class="expense-list">
    <h2>📌 Expenses</h2>
    <ul>
      <li v-for="(expense, index) in expenses" :key="index">
        {{ expense.category }} - ${{ expense.amount }}
        <button @click="$emit('remove-expense', index)" class="remove-btn">❌</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["expenses"],
};
</script>

<style scoped>
.expense-list {
  background: #2d2d42;
  padding: 10px;
  border-radius: 8px;
  margin-bottom: 20px;
}

h2 {
  text-align: center;
  font-size: 1.2rem;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  display: flex;
  justify-content: space-between;
  background: #3b3b5b;
  padding: 10px;
  border-radius: 6px;
  margin: 5px 0;
}

.remove-btn {
  background: #ff4d4d;
  border: none;
  padding: 5px;
  color: white;
  border-radius: 4px;
  cursor: pointer;
}

.remove-btn:hover {
  background: #e60000;
}
</style>
