<template>
    <input type="number" :name="field.name" :value="field.def" class="form-control"/>
</template>

<script>
    export default {
        props: ['field'],
        mounted() {
            console.log('APR-NUMBER mounted.')
        },
        components: {
        }
    }
</script>
