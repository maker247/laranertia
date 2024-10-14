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

    <div class="mt-[400px]">
        <p>The current time is {{ time }}</p>

        <Link
            href="/users"
            class="text-blue-500"
            preserve-scroll
        >
            Refresh
        </Link>
    </div>
</template>

<script setup>

defineProps({
    time: String
})

</script>
