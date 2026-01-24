<template>
    <div>
        <slot></slot>
    </div>


    <div>
        <slot name="header"></slot>
        <slot name="content"></slot>
        <slot name="footer"></slot>
    </div>
</template>

<script>
export default {
    name: 'Card',
    // props: ['content']
}
</script>
