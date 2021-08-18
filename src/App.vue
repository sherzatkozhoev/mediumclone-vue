<template>
    <div>
        <mcv-topbar />
        <router-view />
    </div>
</template>
<script>
import {actionTypes} from '@/store/modules/auth';
import McvTopbar from '@/components/Topbar';

export default {
    name: 'McvApp',
    components: {
        McvTopbar
    },
    mounted() {
        this.$store.dispatch(actionTypes.getCurrentUser);
    }
}
</script>
