<template>
    <Head title="Login User" />

    <h1 class="text-3xl">Login</h1>

    <form
        @submit.prevent="submit"
        class="max-w-md mx-auto mt-8"
    >
        <div class="mb-6">
            <label
                for="email"
            >
                Email
            </label>

            <input
                class="border border-gray-400 p-2 w-full"
                type="email"
                name="email"
                id="email"
                v-model="form.email"
            />

            <div
                v-if="form.errors.email"
                class="text-red-500 text-xs mt-1"
                v-text="form.errors.email"
            ></div>
        </div>

        <div class="mb-6">
            <label
                for="password"
            >
                Password
            </label>

            <input
                class="border border-gray-400 p-2 w-full"
                type="password"
                name="password"
                id="password"
                v-model="form.password"
            />

            <div
                v-if="form.errors.password"
                class="text-red-500 text-xs mt-1"
                v-text="form.errors.password"
            ></div>
        </div>

        <div class="mb-6">
            <button
                type="submit"
                class="bg-blue-400 text-white rounded py-2 px-4 hover:bg-blue-500"
                :class="{'cursor-not-allowed hover:bg-gray-500 bg-gray-500' : form.processing}"
                :disabled="form.processing"
            >
                Submit
            </button>
        </div>
    </form>
</template>

<script>
    export default {
        layout: null
    }
</script>

<script setup>
    import {useForm} from "@inertiajs/inertia-vue3"

    let form = useForm({
        email: '',
        password: ''
    })

    let submit = () => {
        form.post('/login')
    }
</script>
