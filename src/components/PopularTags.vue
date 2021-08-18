<template>
    <div class="sidebar">
        <p>Popular Tags</p>
        <mcv-loading v-if="isLoading" />
        <mcv-error-message v-if="error" />
        <div v-if="popularTags" class="tag-list">
            <router-link
                v-for="(popularTag, index) in popularTags"
                :to="{name: 'tag', params: {slug: popularTag}}"
                class="tag-default tag-pill"
                :key="index"
            >
                {{ popularTag }}
            </router-link>
        </div>
    </div>
</template>
<script>
import {mapState} from 'vuex';
import {actionTypes} from '@/store/modules/popularTags';
import McvLoading from '@/components/Loading';
import McvErrorMessage from '@/components/ErrorMessage';

export default {
    name: 'McvPopularTags',
    components: {
        McvLoading,
        McvErrorMessage
    },
    computed: {
        ...mapState({
            popularTags: state => state.popularTags.data,
            isLoading: state => state.popularTags.isLoading,
            error: state => state.popularTags.error
        })
    },
    mounted() {
        this.$store.dispatch(actionTypes.getPopularTags);
    }
}
</script>