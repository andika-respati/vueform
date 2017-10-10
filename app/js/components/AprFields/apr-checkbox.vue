<template>
    <div>
        <div class="form-check" v-for="item in items">
            <div class="form-check">
                <label class="form-check-label">
                    <input class="form-check-input" type="checkbox" :checked="item.checked" :name="item.id">
                    {{item.name}}
                </label>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['field'],
        mounted() {
            console.log('APR-TEXT mounted.')
        },
        computed: {
            list: function (that = this) {
                return that.field.list
            },
            def: function (that = this) {
                return that.field.def
            },
            items: function (that = this) {
                let data = [];
                for (let key in that.list){
                    let item = {};
                    item.id  = key;
                    item.name = that.list[key];
                    item.checked = that.def[key];
                    data.push(item);
                }
                return data;
            }
        },
        components: {
        }
    }
</script>
