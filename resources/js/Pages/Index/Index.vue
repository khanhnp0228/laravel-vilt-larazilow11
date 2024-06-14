<template>
    <div>Index</div>
    <Link href="/hello">Show Page</Link>
    <div>
        The message is "{{message}}"
    </div>
</template>

<script setup>
import { Link } from '@inertiajs/vue3';

/* Pass params from Laravel to Vue's props */
// Method 1:
// defineProps(['message']);

// Method 2: With validation
defineProps({
    message: String
});
</script>
