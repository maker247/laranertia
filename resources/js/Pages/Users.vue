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
        <table class="table-auto">
            <tbody>
                <tr v-for="user in users.data" :key="user.id">
                    <td>{{ user.name }}</td>
                    <td><Link href="/">Edit</Link></td>
                </tr>
            </tbody>
        </table>

<!--        paginator-->
        <div class="mt-6">
            <Pagination
                :links="users.links"
            />
        </div>
    </div>
</template>

<script setup>
import Pagination from "../Shared/Pagination"

defineProps({
    users: Array
})

</script>
