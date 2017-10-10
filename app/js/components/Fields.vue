<template>
    <div v-if="field.type === 'text'">
        <apr-text :field="field"></apr-text>
    </div>
    <div v-else-if="field.type === 'number'">
        <apr-number :field="field"></apr-number>
    </div>
    <div v-else-if="field.type === 'password'">
        <apr-password :field="field"></apr-password>
    </div>
    <div v-else-if="field.type === 'checkbox'">
        <apr-checkbox :field="field"></apr-checkbox>
    </div>
    <div v-else-if="field.type === 'option'">
        <apr-option :field="field"></apr-option>
    </div>
</template>

<script>
    import text from './AprFields/apr-text.vue'
    import number from './AprFields/apr-number.vue'
    import password from  './AprFields/apr-password.vue'
    import checkbox from './AprFields/apr-checkbox.vue'
    import option from './AprFields/apr-option.vue'

    export default {
        props: ['field'],
        mounted() {
//            console.log('APR-FIELDS mounted.')
        },
        components: {
            'apr-text': text,
            'apr-number': number,
            'apr-password': password,
            'apr-checkbox': checkbox,
            'apr-option': option
        }
    }
</script>
