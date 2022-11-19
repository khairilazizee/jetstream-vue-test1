<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import FormSection from '@/Components/FormSection.vue';



</script>

<template>
    <AppLayout title="Dashboard">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Create User
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <FormSection @submitted="createNewUser">
                        <template #title>
                            Profile Information
                        </template>

                        <template #description>
                            Create new account's profile information and email address.
                        </template>
                    </FormSection>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
