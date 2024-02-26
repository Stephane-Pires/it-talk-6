
<template>
    <div class="note">
        <strong>Note:</strong>
        <slot />
    </div>
</template>

<style scoped>
.note {
    max-width: max-content;
    @apply text-sm font-mono;
}
.note > strong {
    margin-right: 0.5rem;
}
</style>