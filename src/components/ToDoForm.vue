<template>
    <form @submit.prevent="onSubmit">
        <h2 class="label-wrapper"><label for="new-todo-input"> What needs to be done? </label></h2>
        <input class="input__lg" type="text" id="new-todo-input" name="new-todo" autocomplete="off"
            v-model.lazy.trim="label" />
        <button type="submit" class="btn btn__primary btn__lg" @click="launchConfetti">Add</button>
    </form>
</template>

<script>
// Maybe we will come back to this idea //
/* import JSConfetti from 'js-confetti'
const jsConfetti = new JSConfetti() */

export default {
    methods: {
        onSubmit() {
            if (this.label === "") {
                return;
            }
            this.$emit("todo-added", this.label)
            this.label = "";
        },
        // Function to launch confetti //
        /* launchConfetti() {
            jsConfetti.addConfetti({
                confettiColors: ['#ff0a54', '#ff477e', '#ff7096', '#ff85a1', '#fbb1bd', '#f9bec7'],
                confettiRadius: 6,
                confettiNumber: 100,
            })
        }, */
    },
    data() {
        return {
            label: "",
        };
    }
};
</script>