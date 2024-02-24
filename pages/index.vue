<script setup>
useHead({
    title: 'Mevea zadanie',
    description: 'Zadanie pre agenturu Mevea'
})

onMounted(() => {
    window.scrollTo(0, 0);
});
</script>

<template>
    <div class="home">
       <PartialsHeroSection />
       <PartialsBoxesSection />
    </div>
</template>
