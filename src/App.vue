<template>
    <div class="wrapper">
        <form @submit="onSubmit">
            <h1>テキスト置換！</h1>
            <MyInput ref="prev" label="置換前のテキスト"></MyInput>
            <MyInput ref="after" label="置換後のテキスト"></MyInput>

            <p class="attention">※実行をクリックするとアートボード直下のテキストのみが置換されます。</p>
            <footer>
                <button uxp-variant="cta" @click="onClickExecution">実行</button>
                <button type="submit" @click="onCancelHandler">キャンセル</button>
            </footer>
        </form>
    </div>
</template>
<script>
    import MyInput from './MyInput.vue';
    export default {
        components: {
            MyInput,
        },
        props: {
            dialog: {
                type: Object,
                required: true,
            },
        },
        methods: {
            onSubmit(e) {
                e.preventDefault();
            },
            onCancelHandler() {
                this.dialog.close();
            },
            onClickExecution() {
                this.dialog.close([this.$refs.prev.getValue(), this.$refs.after.getValue()]);
            },
        },
    }
</script>
<style scoped>
    .wrapper {
        width: 300px;
    }

    .attention {
        color: #999;
        font-size: 12px;
    }
</style>