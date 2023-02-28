<template>
    <form @submit.prevent="formHandler">
        <input type="text" name="description" placeholder="Description..." v-model="formData.desc">
        <input type="number" name="price" placeholder="Value..." v-model="formData.price">
        <input type="date" name="date" placeholder="Date..." v-model="formData.date">
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
                price: formData.price,
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