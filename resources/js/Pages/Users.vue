<template>
    <Head>
        <title>Users</title>
        <meta
            type="description"
            content="Information for Users my app"
            head-key="description"
        >
    </Head>

    <h1 class="text-4xl font-bold">Users</h1>

    <div class="mt-8">
        <ul>
            <li v-for="user in users" :key="user.id" v-text="user.name"></li>
        </ul>
    </div>
</template>

<script setup>

defineProps({
    users: Array
})

</script>
