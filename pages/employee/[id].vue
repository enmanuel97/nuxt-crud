<template>
    <div>
        <p>employee id page</p>
    </div>
</template>

<script setup>
    const { id } = useRoute().params;

    console.log(id)
</script>