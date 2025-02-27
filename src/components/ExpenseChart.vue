<template>
  <div class="chart-wrapper">
    <h2 class="chart-title">📊 Expense Overview</h2>
    <div class="chart-container">
      <Bar v-if="expenses.length" :data="chartData" :options="chartOptions" />
      <p v-else class="no-data">No expenses to show.</p>
    </div>
  </div>
</template>

<script>
import { defineComponent, computed, watch } from "vue";
import { Chart as ChartJS, BarElement, CategoryScale, LinearScale, Title, Tooltip, Legend } from "chart.js";
import { Bar } from "vue-chartjs";

// Register ChartJS Components
ChartJS.register(CategoryScale, LinearScale, BarElement, Title, Tooltip, Legend);

export default defineComponent({
  components: { Bar },
  props: { expenses: Array },
  setup(props) {
    const chartData = computed(() => ({
      labels: props.expenses.map(e => e.category),
      datasets: [
        {
          label: "Expenses",
          data: props.expenses.map(e => e.amount),
          backgroundColor: ["#A78BFA", "#8B5CF6", "#6D28D9", "#4C1D95"],
          borderRadius: 5,
        },
      ],
    }));

    const chartOptions = {
      responsive: true,
      maintainAspectRatio: false,
      plugins: { legend: { display: true } },
    };

    return { chartData, chartOptions };
  },
});
</script>

<style scoped>
.chart-wrapper {
  background: #1e1e2f;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  margin-top: 20px;
  color: white;
}

.chart-title {
  font-size: 1.2rem;
  font-weight: bold;
  text-align: center;
  margin-bottom: 10px;
}

.chart-container {
  width: 100%;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.no-data {
  text-align: center;
  font-size: 1rem;
  color: #aaa;
}
</style>
