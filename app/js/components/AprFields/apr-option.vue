<template>
    <div>
        <div class="form-check" v-for="item in items">
            <label class="form-check-label">
                <input class="form-check-input" type="radio" :name="field.name" :value="item.id" :checked="item.checked">
                {{item.name}}
            </label>
        </div>
        <!--<div class="form-check">-->
            <!--<label class="form-check-label">-->
                <!--<input class="form-check-input" type="radio" name="exampleRadios" id="exampleRadios2" value="option2">-->
                <!--Option two can be something else and selecting it will deselect option one-->
            <!--</label>-->
        <!--</div>-->
        <!--<div class="form-check disabled">-->
            <!--<label class="form-check-label">-->
                <!--<input class="form-check-input" type="radio" name="exampleRadios" id="exampleRadios3" value="option3" disabled>-->
                <!--Option three is disabled-->
            <!--</label>-->
        <!--</div>-->
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
                    item.checked = (key===that.def);
                    data.push(item);
                }
                return data;
            }
        },
        components: {
        }
    }
</script>
