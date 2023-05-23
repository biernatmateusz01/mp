<template>
  <button class="button">
    <slot />
  </button>
</template>


<style scoped>
.button{
    background: rgb(28, 28, 224);
    padding: 8px 16px;
    border: none;
    color: white;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    border: 1px solid transparent;
    transition: all .4s;
}
.button:hover{
    background: white;
    color: rgb(28, 28, 224);
    border: 1px solid rgba(28, 28, 224)
}
</style>