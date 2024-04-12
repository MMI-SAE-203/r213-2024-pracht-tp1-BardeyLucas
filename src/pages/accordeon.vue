<script setup lang="ts">
import { ref } from 'vue'
const sectionOpen = ref(1)

</script>

<template>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen==1">bouton 1</button>
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Blanditiis, incidunt eveniet atque nesciunt eligendi inventore? Quas ut ab mollitia eligendi, eum repellendus laudantium esse cumque fugit laborum excepturi officia eaque.</p>
    </section>
    <section>
        <button class=" text-xl">bouton 2</button>
        <p>Ut tenetur nam dolore. Accusamus reiciendis iusto eligendi numquam facilis dolores. Ex, unde reiciendis eos,
            autem officia amet mollitia harum ullam fugiat atque, odio nemo impedit maiores officiis aut sunt!</p>
    </section>
    <section>
        <button class="text-xl">bouton 3</button>
        <p>Impedit tempora dolores esse pariatur temporibus nam! Tempora molestias eius voluptatibus enim, ducimus dicta
            laborum suscipit possimus neque a quo dignissimos expedita quae sit sed voluptates magni inventore natus at.
        </p>
    </section>
</template>