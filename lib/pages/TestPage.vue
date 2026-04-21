<script setup lang="ts">
import { Common } from 'vt:@core/components/Common';
import { ref } from 'vue';
interface Props {
    test: string
}

const props = defineProps<Props>()

console.log("WORKS!")

function clickTest() {
    console.log("CLICKED ME")
    someState.value = !someState.value
}


const someState = ref(false)
const text = ref("nothing yet")

</script>
<template>
    <Group class="z-30 wrap-normal" :anchor="{ Full: 1, Left: 0, Right: 0 }">
        <Label>Test {{ props.test }}</Label>
        <Common.BackButton :anchor="{ Top: 1 }"></Common.BackButton>
        <CheckBox :anchor="{}"></CheckBox>
    </Group>
</template>
<style>
.test {}
</style>
