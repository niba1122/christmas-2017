<template>
    <image :xlink:href="src"
           :width="width"
           :height="height"
           :x="x"
           :y="y"
           @mousedown="handleMouseDown"
           />
</template>
<script>

export default {
    props: ['src', 'isSelected', 'width', 'height', 'initialX', 'initialY'],
    data() {
        return {
            isMouseDown: false,
            beforeMouseX: null,
            beforeMouseY: null,
            x: this.initialX,
            y: this.initialY
        }
    },
    components: {
    },
    mounted() {
        document.addEventListener('mouseup', this.handleMouseUp)
        document.addEventListener('mousemove', this.handleMouseMove)
    },
    unmounted() {
        document.removeEventListener('mouseup', this.handleMouseUp)
        document.removeEventListener('mousemove', this.handleMouseMove)
    },
    methods: {
        handleMouseDown(event) {
            event.preventDefault();
            this.isMouseDown = true
        },
        handleMouseUp(event) {
            this.isMouseDown = false
        },
        handleMouseMove(event) {
            if (!this.isMouseDown) return
		    let mouseX = event.clientX
            let mouseY = event.clientY
            let dx = 0;
            let dy = 0;
            if (this.beforeMouseX && this.beforeMouseY) {
                dx = mouseX - this.beforeMouseX
                dy = mouseY - this.beforeMouseY
            }
            this.beforeMouseX = mouseX
            this.beforeMouseY = mouseY
            this.x += dx
            this.y += dy
        }
    }
}
</script>