<template>
    <div class="container mx-auto mt-10">
        <div class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
            <h1 class="text-3xl font-bold mb-6">Create new employee</h1>
            <form @submit.prevent="createItem" class="mb-0 space-y-4">
                <div>
                    <label for="first_name" class="block text-gray-700 text-sm font-bold mb-2">
                        First Name
                    </label>
                    <input 
                        type="text"
                        id="first_name"
                        v-model="newItem.firstName"
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="First Name"
                    />
                </div>
                <div>
                    <label for="last_name" class="block text-gray-700 text-sm font-bold mb-2">
                        Last Name
                    </label>
                    <input 
                        type="text" 
                        id="last_name" 
                        v-model="newItem.lastName"
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="Last Name"
                    />
                </div>
                <div>
                    <label for="salary" class="block text-gray-700 text-sm font-bold mb-2">
                        Salary
                    </label>
                    <input
                        id="salary"
                        type="text"
                        v-model="newItem.salary"
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="Salary"
                    />
                </div>
                <div>
                    <label for="date" class="block text-gray-700 text-sm font-bold mb-2">
                        Date
                    </label>
                    <input 
                        id="date"
                        type="date"
                        v-model="newItem.date"
                        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        placeholder="Salary"
                    />
                </div>
            </form>
        </div>
    </div>
</template>

<script setup>
    const router = useRoute();
    const newItem = reactive({
        id: Date.now(),
        firstName: '',
        lastName: '',
        salary: '',
        date: ''
    })

    const createItem = async () => {
        let items = JSON.parse(localStorage.getItem('items')) || [];
        items.push(newItem);
        localStorage.setItem('items', JSON.stringify(items));
        await navigateTo('/employee');
    }
</script>