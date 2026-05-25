<script setup lang="ts">
import { Common } from 'vt:@core/components/Common';
import { Core } from 'vt:@core/components/core';
import { useData } from 'vt:@core/composables/useData';
import { ref } from 'vue';

console.log("WORKS!")

function clickTest() {
    console.log("CLICKED ME")
    someState.value = !someState.value
}

const textFieldInput = ref("Hello!")

const someState = ref(false)
const text = ref("nothing yet")

const test = useData<string>("test", "default value")

</script>
<template>

    <Common.DecoratedContainer :anchor="{ Bottom: 50, Width: 1000, Height: 250 }">
        <template #title>
            <Common.Title :text="text" />
        </template>

        <template #content>
            <Group layout-mode="Left">
                <Group layout-mode="Middle" :flex-weight="1">
                    <Label :text="text" :el-style="{ Alignment: 'Center', Wrap: true, FontSize: 20 }" />
                </Group>
                <Common.DecoratedContainer :anchor="{ Width: 300, Height: 250, Top: -55 }">
                    <template #title>
                        <Common.Title :text="test" />
                    </template>
                    <template #content>
                        <Group :anchor="{}">
                            <Common.TextButton text="I found the treasure!" @activating="clickTest" />
                        </Group>
                    </template>
                </Common.DecoratedContainer>
            </Group>
        </template>

    </Common.DecoratedContainer>
    <Common.BackButton />
</template>
