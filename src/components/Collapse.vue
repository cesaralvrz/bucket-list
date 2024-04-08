<template>
    <div 
        tabindex="0" 
        class="collapse collapse-arrow border border-green-600"
        :class="collapseState"
        @click="changeCollapseState"
    >
        <div class="collapse-title text-xl font-medium">
            {{ collapseTitle }}
        </div>
        <div class="collapse-content"> 
            <slot />
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from "vue"

const props = defineProps({
  icon: {
    type: String,
    required: false,
  },
  title: {
    type: String,
    required: false,
  },
})

const collapseState = ref("collapse-close")

const collapseTitle = computed(() =>  
    `${props.icon} ${props.title}`
)

function changeCollapseState() {
    if (collapseState.value === "collapse-close") {
        collapseState.value = "collapse-open"
    } else if (collapseState.value === "collapse-open") {
        collapseState.value = "collapse-close"
    }
}
</script>