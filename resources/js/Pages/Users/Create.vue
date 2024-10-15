<template>
    <Head title="Create User" />

    <h1 class="text-3xl">Create New User</h1>

    <form
        @submit.prevent="submit"
        class="max-w-md mx-auto mt-8"
    >
        <div class="mb-6">
            <label
                for="name"
            >
                Name
            </label>

            <input
                class="border border-gray-400 p-2 w-full"
                type="text"
                name="name"
                id="name"
                v-model="form.name"
            />

            <div
                 v-if="errors.name"
                 class="text-red-500 text-xs mt-1"
                 v-text="errors.name"
            ></div>
        </div>

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
                v-if="errors.email"
                class="text-red-500 text-xs mt-1"
                v-text="errors.email"
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
                v-if="errors.password"
                class="text-red-500 text-xs mt-1"
                v-text="errors.password"
            ></div>
        </div>

        <div class="mb-6">
            <button
                type="submit"
                class="bg-blue-400 text-white rounded py-2 px-4 hover:bg-blue-500"
            >
                Submit
            </button>
        </div>
    </form>
</template>

<script setup>
    import {reactive} from "vue"
    import {Inertia} from "@inertiajs/inertia"

    defineProps({
        errors: Object
    })

    let form = reactive({
        name: '',
        email: '',
        password: ''
    })

    let submit = () => {
        Inertia.post('/users', form)
    }

</script>
