<template>
    <input type="text" :name="field.name" :value="field.def" class="form-control"/>
</template>

<script>
    export default {
        props: ['field'],
        mounted() {
            console.log('APR-TEXT mounted.')
        },
        components: {
        }
    }
</script>
