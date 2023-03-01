<template>
    <form @submit.prevent="formHandler">
        <input type="text" placeholder="Description..." v-model="formData.desc">
        <input type="number" placeholder="Value..." v-model="formData.price">
        <input type="date" value="dd/mm/yyyy" placeholder="Date..." v-model="formData.date">
        <input type="submit" value="Submit">
    </form>
</template>

<script>
import { reactive } from 'vue';
export default {
    props: {
        state: Object
    },
    setup(props, { emit }) {
        const formData = reactive({
            desc: null,
            price: null,
            date: null
        });

        function formHandler() {
            emit("add-income", {
                desc: formData.desc,
                price: parseInt(formData.price),
                date: formData.date
            });

            formData.desc = null;
            formData.price = null;
            formData.date = null;
        }
        return {
            formData,
            formHandler
        }
    }

}
</script>

<style scoped></style>