<template>
  <div class="welcome-container">
    <h1>Welcome to Your Expense Tracker</h1>
    <p>Track your spending efficiently and gain financial control.</p>
    
    <router-link to="/dashboard">
      <button class="start-btn">Get Started</button>
    </router-link>
  </div>
</template>

<style scoped>
.welcome-container {
  text-align: center;
  padding: 50px;
  background: #f5e8ff; /* Light Lavender */
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h1 {
  color: #6a0dad; /* Deep Purple */
  font-size: 32px;
  margin-bottom: 10px;
}

p {
  color: #4a0072;
  font-size: 18px;
  margin-bottom: 20px;
}

.start-btn {
  background: #6a0dad;
  color: white;
  border: none;
  padding: 12px 24px;
  font-size: 18px;
  cursor: pointer;
  border-radius: 8px;
  transition: 0.3s ease-in-out;
}

.start-btn:hover {
  background: #5a0080;
}
</style>
