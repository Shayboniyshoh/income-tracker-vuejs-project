<template>
    <div class="income-item">
        <div class="removeItem">x</div>
        <div class="desc">{{ income.desc }}</div>
        <div class="price">$ {{ income.price }}</div>
        <div class="date">{{ formattedDate }}</div>
    </div>
</template>

<script>
export default {
    props: {
        income: Object
    },
    setup(props) {
        let date = new Date(props.income.date);
        let day = date.getDay();
        let month = date.getMonth();
        let year = date.getFullYear();

        let formattedDate = day + "/" + month + "/" + year;
        console.log(formattedDate);
        return {
            formattedDate,
        }
    }
}
</script>

<style scoped></style>