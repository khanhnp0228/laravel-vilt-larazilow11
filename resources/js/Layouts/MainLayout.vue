<template>
    <Link href="/">Main Page</Link>&nbsp;
    <Link href="/hello">Show Page</Link>&nbsp;
    <Link href="/listing">Listing</Link>&nbsp;
    <Link href="/listing/create">New Listing</Link>&nbsp;
    <div>The page with time {{ timer }}</div>

    <div v-if="flashSuccess" class="success">
        {{ flashSuccess }}
    </div>

    <slot></slot>
</template>

<script setup>
import { Link, usePage } from '@inertiajs/vue3';
import { ref, computed } from 'vue';

const timer = ref(0);
setInterval(() => timer.value++, 1000);

// page.props.flash.success
const page = usePage()
const flashSuccess = computed(
    () => page.props.flash.success
)

</script>

<style scoped>
.success {
    background-color: green;
    color: #fff;
}
</style>
