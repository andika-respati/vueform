<template>
    <form :action="config.action" :method="config.method" v-on:submit.prevent="onSubmit">
        <div v-for="field in config.fields" class="form-group row">
            <label class="col-sm-2 col-form-label" v-if="field.label">{{field.label}}</label>
            <apr-fields :field="field" class="col-md-10"></apr-fields>
        </div>

        <!--<apr-fields v-for="field in config.fields" :field="field"></apr-fields>-->
        <button type="submit" class="btn btn-primary">{{submitText}}</button>
    </form>
</template>

<script>
    import fields from './Fields.vue';

    export default {
        props: ['config'],
        mounted() {
            console.log('APR-FORM mounted.')
        },
        computed: {
            submitText: function () {
                return "Simpan"
            }
        },
        components: {
            'apr-fields': fields
        },
        methods:{
            onSubmit: function (e) {
                e.preventDefault();
                console.log( $(this.$el).serialize() )
            }
        }
    }
</script>
