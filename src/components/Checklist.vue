<template>
    <div>
        <h3>{{ cookedTitle }}</h3>
        <div 
            v-for="(item, key) in list"
            :key="key"
        >
            <div class="flex ml-6 mt-2">
                <!-- If you want to check/uncheck remove disabled property -->
                <input
                    v-if="item?.checked"
                    type="checkbox" 
                    class="checkbox mr-2" 
                    disabled
                    checked
                />

                <input
                    v-else
                    type="checkbox" 
                    class="checkbox mr-2" 
                    disabled
                />

                <p>{{ item.text }}</p>
            </div>
        </div>
    </div>
</template>

<script setup>
import { computed } from "vue"

const props = defineProps({
  title: {
    type: String,
    required: false,
  },
  icon: {
    type: String,
    required: false,
  },
  list: {
    type: Array,
    default: () => []
  }
})

const cookedTitle = computed(() => 
    `${props.icon} ${props.title}`
)
</script>