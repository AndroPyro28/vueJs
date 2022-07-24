<template>
    <div>
        This is a modal
        <input type="text" v-model="name">
        <button @click="$emit('closeModal', name)">Close Modal</button>
    </div>
</template>

<script>
    export default {
        name:'ModalComponent',
        emits:{
            closeModal: (name) => {

                if(!name) {
                    return false
                }

                return true;
            }
        },
        data() {
            return {
                name: ''
            }
        }

    }
</script>

<style lang="scss" scoped>

</style>