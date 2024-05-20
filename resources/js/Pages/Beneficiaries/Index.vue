<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import Welcome from '@/Components/Welcome.vue';
defineProps({
    users: Array,
});
</script>

<template>
    <AppLayout title="Beneficiarios">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 dark:text-gray-200 leading-tight">
                Beneficiarios
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white dark:bg-gray-800 overflow-hidden shadow-xl sm:rounded-lg">

                    <div class="p-6 lg:p-8 bg-white dark:bg-gray-800 dark:bg-gradient-to-bl dark:from-gray-700/50 dark:via-transparent border-b border-gray-200 dark:border-gray-700">

                        <h1 class="mt-1 text-2xl font-medium text-gray-900 dark:text-white">
                            Vista de beneficiarios
                        </h1>

                        <p class="mt-6 text-gray-500 dark:text-gray-400 leading-relaxed">
                            Laravel Jetstream provides a beautiful, robust starting point for your next Laravel application. Laravel is designed
                            to help you build your application using a development environment that is simple, powerful, and enjoyable. We believe
                            you should love expressing your creativity through programming, so we have spent time carefully crafting the Laravel
                            ecosystem to be a breath of fresh air. We hope you love it.
                        </p>

                        <br>
                        <br>

                        <div class="flex place-content-center">
                            <div class="">
                                <Link href="/beneficiaries/create" class="inline-block bg-green-800 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mr-2 mb-1">
                                    + Añadir Beneficiario
                                </Link>
                            </div>
                        </div>
                        <br/>
                        <div class="">
                            <table class="">
                                <thead >
                                    <tr class="mt-1 text-base text-gray-900 dark:text-white">
                                        <th class="w-1/12 px-4 py-2 hidden sm:table-cell">Id</th>
                                        <th class="w-1/4 px-4 py-2">Nombre</th>
                                        <th class="w-1/4 px-4 py-2">Correo</th>
                                        <th class="w-1/6 px-4 py-2 hidden sm:table-cell">Creación</th>
                                        <th class="w-1/6 px-4 py-2">Acciones</th>
                                    </tr>
                                </thead>
                                <tbody class="mt-6 text-gray-900 dark:text-gray-300 leading-relaxed">
                                    <tr v-for="user in users" :key="user.id">
                                        <td class="border dark:border-gray-500 whitespace-normal break-all px-4 py-2 hidden sm:table-cell">{{ user.id }}</td>
                                        <td class="border dark:border-gray-500 whitespace-normal break-all px-4 py-2">{{ user.name }}</td>
                                        <td class="border dark:border-gray-500 whitespace-normal break-all px-4 py-2">{{ user.email }}</td>
                                        <td class="border dark:border-gray-500 whitespace-normal break-all px-4 py-2 hidden sm:table-cell">{{ user.created_at }}</td>
                                        <td class="border dark:border-gray-500 md:flex md:items-center px-4 py-2">
                                            <div class="">
                                                <Link :href="'/beneficiaries/'+user.id+'/edit'" class="inline-block bg-blue-500 hover:bg-blue-700 text-white font-bold px-2 py-2 rounded mr-2 mb-1">Editar</Link>
                                            </div>
                                            <div class="">
                                                <Link :href="'/beneficiaries/'+user.id+'/delete'" class="inline-block bg-red-500 hover:red-blue-700 text-white font-bold px-2 py-2 rounded">Eliminar</Link>
                                            </div>
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>


                    </div>






                    <div class="font-sans text-gray-900 antialiased">
                        <div class="pt-4 bg-gray-100">
                            <div class="min-h-screen flex flex-col items-center pt-6 sm:pt-0">

                                <Link href="/beneficiaries/create" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"> Añadir Beneficiario </Link>
                                <table class="table-fixed">
                                    <thead>
                                        <tr>
                                            <th class="w-1/12 px-4 py-2">Id</th>
                                            <th class="w-1/4 px-4 py-2">Nombre</th>
                                            <th class="w-1/4 px-4 py-2">Correo</th>
                                            <th class="w-1/6 px-4 py-2">Creación</th>
                                            <th class="w-1/6 px-4 py-2">Acciones</th>
                                        </tr>
                                    </thead>
                                    <tbody>
                                        <tr v-for="user in users" :key="user.id">
                                            <td class="border px-4 py-2">{{ user.id }}</td>
                                            <td class="border px-4 py-2">{{ user.name }}</td>
                                            <td class="border px-4 py-2">{{ user.email }}</td>
                                            <td class="border px-4 py-2">{{ user.created_at }}</td>
                                            <td class="md:flex md:items-center border px-4 py-2">
                                                <div class="">
                                                    <Link :href="'/beneficiaries/'+user.id+'/edit'" class="block bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mr-2 mb-1">Editar</Link>
                                                </div>
                                                <div class="">
                                                    <Link :href="'/beneficiaries/'+user.id+'/delete'" class="block bg-red-500 hover:red-blue-700 text-white font-bold py-2 px-4 rounded">Eliminar</Link>
                                                </div>
                                            </td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>
                        </div>
                    </div>


                </div>
            </div>
        </div>
    </AppLayout>
</template>
