<template>
  <div class="max-w-2xl px-6 py-12 mx-auto text-gray-800">
    <hero />
    <collapse 
      v-for="(item, key) in bucketList"
      :key="key"
      :title="item.title"
      :icon="item.icon"
      class="my-4"
    >
      <checklist
        v-for="(checklist, key) in item.checklists"
        :key="key"
        :title="checklist.title"
        :icon="checklist.icon"
        :list="checklist.list"
        class="my-4"
      />
    </collapse>

    <!-- TODO -->
    <collapse
      title="Travel"
      icon="✈️"
    />
  </div>
</template>

<script setup>
import Hero from "./components/Hero.vue"
import Collapse from "./components/Collapse.vue"
import Checklist from "./components/Checklist.vue"

const bucketList = [
  {
    title: "Professional Career",
    icon: "💼",
    checklists: [
      {
        title: "Education journey",
        icon: "🎓",
        list: [
          { 
            checked: true, 
            text: 'Graduate from Universidad Pontificia de Salamanca',
          },
        ]
      },
      {
        title: "Employee Journey",
        icon: "👔",
        list: [
          { 
            checked: true, 
            text: 'Land first job',
          },
          { 
            checked: false, 
            text: 'Become a Senior Software Engineer',
          },
          { 
            checked: false, 
            text: 'Work at FAANG',
          },
        ]
      },
      {
        title: "Founder Journey",
        icon: "⛰️",
        list: [
          { 
            checked: false, 
            text: 'Create my own startup',
          },
          { 
            checked: false, 
            text: '>100k€/year',
          },
        ]
      },
    ]
  },
  {
    title: "Sports and Activity",
    icon: "🏄‍♂️",
    checklists: [
      {
        title: "Strength",
        icon: "🏋️",
        list: [
          { 
            checked: true, 
            text: 'Pistol squat' 
          },
          { 
            checked: false, 
            text: 'L-Sit hold (>30s)' 
          },
          { 
            checked: false, 
            text: 'Muscle-up' 
          },
          { 
            checked: false, 
            text: 'Handstand' 
          },
          { 
            checked: false, 
            text: 'Planche' 
          },
          { 
            checked: false, 
            text: '180kg deadlift (1RM)' 
          },
          { 
            checked: false, 
            text: '120kg squat (1RM)' 
          },
        ]
      },
      {
        title: "Endurance",
        icon: "🏃‍♂️",
        list: [
          { 
            checked: false, 
            text: 'Run half-marathon' 
          },
          { 
            checked: false, 
            text: 'Run marathon' 
          },
          { 
            checked: false, 
            text: 'Do an Ironman' 
          },
        ]
      },
      {
        title: "Board sports",
        icon: "🏂",
        list: [
          { 
            checked: true, 
            text: 'Ollie on Skateboard' 
          },
          { 
            checked: false, 
            text: 'Kickflip on Skateboard' 
          },
          { 
            checked: false, 
            text: 'Boardslide on Snowboard' 
          },
        ]
      },
      {
        title: "BJJ",
        icon: "🥋",
        list: [
          { 
            checked: false, 
            text: 'Start BJJ' 
          },
          { 
            checked: false, 
            text: 'Blue belt' 
          },
          { 
            checked: false, 
            text: 'Black belt' 
          },
        ]
      },
    ]
  },
  {
    title: "Miscellaneous",
    icon: "🎲",
    checklists: [
      {
        title: "Personal development",
        icon: "🪴",
        list: [
          { 
            checked: false, 
            text: 'Read 100 books',
          },
          { 
            checked: false, 
            text: 'Write a book',
          },
          { 
            checked: false, 
            text: 'Plant a tree',
          },
          { 
            checked: false, 
            text: 'Be a father',
          },
        ]
      },
      {
        title: "Fun",
        icon: "🪂",
        list: [
          { 
            checked: false, 
            text: 'Skydive',
          },
          { 
            checked: false, 
            text: 'Do El Camino de Santiago',
          },
        ]
      },
    ]
  },
]

</script>
