<script setup>
</script>

<template>
    <div class="footer">
        <img src="../assets/logo-fabrica.svg" alt="Logo da Fábrica" />
        <img src="../assets/logo-github.svg" alt="Logo do Github" />
    </div>
</template>

<style scoped>
.footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 44px;
    background-color: #1C1C1C;
}

@media (max-width: 768px) {
    .footer {
        display: flex;
        justify-content: space-between;
        padding: 20px;
    }
    .footer img {
        height: 2rem;
    }
}
</style>