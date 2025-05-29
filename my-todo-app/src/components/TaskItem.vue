<template>

    <div class="card shadow-sm my-2">

        <div class="card-body d-flex justify-content-between align-items-center">

            <span>{{ task.text }}</span>

            <!-- TODO: gestire modifica ed eliminazione -->
            <div>
                <!-- edit -->
                <button class="btn btn-sm btn-warning me-2" @click="$emit('edit')">Edit</button>

                <!-- eliminazione task -->
                <button class="btn btn-sm btn-danger" @click="$emit('remove')">Delete</button>
            </div>

        </div>


    </div>




</template>

<script>
export default {
    props: ['task']
}

</script>

<style scoped></style>