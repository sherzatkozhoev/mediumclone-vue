<template>
    <ul class="pagination">
        <li
            v-for="page in pages"
            class="page-item"
            :class="{active: page === currentPage}"
            :key="page"
        >
            <router-link :to="{path: url, query: {page: page}}" class="page-link">
                {{ page }}
            </router-link>
        </li>
        &nbsp;
    </ul>
</template>

<script>
import {range} from '@/helpers/utils';

export default {
    name: 'McvPagination',
    props: {
        total: {
            type: Number,
            required: true
        },
        limit: {
            type: Number,
            required: true
        },
        currentPage: {
            type: Number,
            required: false,
        },
        url: {
            type: String,
            required: true
        }
    },
    computed: {
        pages() {
            const pagesCount = Math.ceil(this.total / this.limit);
            return range(1, pagesCount);
        }
    }
}
</script>