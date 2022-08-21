<template>
    <dialog open>
        <slot></slot>
    </dialog>
</template>

<style scoped>
dialog{
    margin: 0%;
    top: 20vh;
    left: 30%;
    width: 40%;
    background-color: white;
    position: fixed;
    padding: 1rem;
    box-shadow: 0 2px  8px rgba(0, 0, 0, 0.26);
}
</style>