<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';

defineProps({
    users: Array
})
</script>

<template>
    <AppLayout title="Dashboard">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Users Information
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="text-right mb-4" v-if="$page.props.permission.users.create">
                    <a :href="route('users.create')">
                        <PrimaryButton>Create User</PrimaryButton>
                    </a>
                </div>
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <table class="w-full p-4">
                        <thead class="bg-gray-400">
                            <tr>
                                <th class="p-2 text-left">Name</th>
                                <th class="text-left">Email</th>
                                <th class="text-center">Status</th>
                                <th class="text-center">Role</th>
                                <th></th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="user in users" :key="user.id">
                                <td class="p-2">{{ user.name }}</td>
                                <td>{{ user.email }}</td>
                                <td class="text-center">Active</td>
                                <td class="text-center">{{ user.role }}</td>
                                <td class="text-center">
                                    <a :href="route('users.edit', user.id)" v-if="user.can.update"
                                        class="text-indigo-600 hover:text-indigo-900">Edit</a>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
