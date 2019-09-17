<template>
    <div>
        <b-button  size="sm" :variant="variant" @click="$emit('clickOnBtn')">{{ label }}</b-button>
    </div>
</template>

<script>
export default {
    created() {
        this.$emit('created');
    },
    props: {
        label: {type: String, default: ''},
        variant: {type: String, dafault: ''}
    }
}
</script>

<style scoped>
    .btn {
        margin: 0 5px 0 0;
    }
</style>