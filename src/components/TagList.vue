<template>
    <ul class="tag-list">
        <li v-for="tag in tags" class="tag-default tag-pill tag-outline" :key="tag">
            {{ tag }}
        </li>
    </ul>
</template>
<script>
export default {
    name: 'McvTagList',
    props: {
        tags: {
            type: Array,
            required: true
        }
    }
}
</script>