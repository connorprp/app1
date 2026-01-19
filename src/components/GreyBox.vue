<template>
    <div id="box">
        <slot></slot>
    </div>
</template>

<style scoped>

#box {
    background-color: #DCDCDC;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 300px;
    height: 100%;
    width: 100%;
}
.curve {
    border-top-right-radius: 100%;
}
</style>
