<template>
    <div class="controller-wrapper" v-on:click="controllerClick">
    </div>
</template>

<script>
    export default {
        name: 'ControllerComponent',
        methods: {
            controllerClick() {
                this.$emit('addTimer')
            }
        }
    }
</script>


<style scoped>
    .controller-wrapper {
        
        width: 22.5rem;
        height: 12rem;
        
        background: #696969;
        
        position: relative;
    
        cursor: pointer;
    }

    .controller-wrapper::after {
        content: '';
        
        position: absolute;
        left: 50%;
        top: 50%;
        
        width: .3rem;
        height: 2rem;
        
        transform: translate(-50%, -50%) rotate(90deg);
        
        background: #9E9E9E;
    }
    .controller-wrapper::before {
        content: '';
        
        position: absolute;
        left: 50%;
        top: 50%;
        
        width: .3rem;
        height: 2rem;
        
        transform: translate(-50%, -50%);
        
        background: #9E9E9E;
    }

</style>