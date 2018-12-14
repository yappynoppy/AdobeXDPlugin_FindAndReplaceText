<template>
    <label>{{ label }}
    <input ref="textField" type="text" size="30" maxlength="20">
    </label>
</template>
<script>
    export default {
        props: {
            label: {
                type: String,
                required: true,
            },
        },
        methods: {
            getValue: function(){
                return this.$refs.textField.value;
            },
        },
    }
</script>