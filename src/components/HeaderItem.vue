<template>
    <header>
        <h1 class="heading">Income Tracker</h1>
        <div class="total-income">${{ totalIncome }}</div>
    </header>
</template>

<script>
export default {
    props: {
        totalIncome: Number
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #333;
    border-bottom: 10px solid #FFCE00;
}

.heading {
    color: #eee;
    padding: 1rem;
}

.total-income {
    color: #eee;
    padding: 1rem;
    font-size: 1.8rem;
    font-weight: 900;
}
</style>