<template>
    <div>{{ message }}</div>
</template>
<script>
export default {
    name: 'McvErrorMessage',
    props: {
        message: {
            type: String,
            required: false,
            default: 'Whoops something went wrong.'
        }
    }
}
</script>