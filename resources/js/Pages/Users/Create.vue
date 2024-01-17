<script setup>
import { router } from "@inertiajs/vue3";
import { reactive } from "vue";

let form = reactive({
    first_name: '',
    last_name: '',
    email: '',
});
function submit() {
    router.post('/users', form)
}
</script>

<template>
    <form @submit.prevent="submit">
        <div>
            <label for="first_name">First Name</label>
            <input type="text" name="first_name" v-model="form.first_name">
        </div>
        <div>
            <label for="last_name">Last Name</label>
            <input type="text" name="last_name" v-model="form.last_name">
        </div>
        <div>
            <label for="email">Email</label>
            <input type="text" name="email" v-model="form.email">
        </div>
        <button>submit</button>
    </form>
</template>

<style scoped></style>
