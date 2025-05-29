<template>

    <div class="modal fade show d-block" tabindex="-1" style="background: rgba(0,0,0,0.5);">

        <div class="modal-dialog">

            <div class="modal-content">

                <div class="modal-header">
                    <h5>Edit Task</h5>

                    <!-- TODO: gestire chiusura della modale -->
                    <button type="button" class="btn-close"></button>
                </div>

                <div class="modal-body">
                    <input type="text" class="form-control">
                </div>

                <div class="modal-footer">
                    <!-- TODO: gestire chiusura della modale / annullamento -->
                    <button class="btn btn-secondary">Close</button>

                    <!-- TODO: gestire il salvataggio della modifica -->
                    <button class="btn btn-primary">Save Changes</button>
                </div>

            </div>

        </div>

    </div>

</template>

<script>

export default {
    props: ['task'], // task che vado a modificare 
    data() {
        return {}
    },
    methods: {}
}
</script>

<style scoped></style>