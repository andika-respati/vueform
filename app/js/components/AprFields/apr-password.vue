<template>
    <input type="password" :name="field.name" :value="field.def" class="form-control"/>
</template>

<script>
    export default {
        props: ['field'],
        mounted() {
            console.log('APR-PASSWORD mounted.')
        },
        components: {
        }
    }
</script>
