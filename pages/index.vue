
<template>
  <div class="min-h-screen max-w-5xl mx-auto dark:bg-gray-900 dark:text-white p-6">
    <h1 class="text-3xl font-bold flex items-center gap-2 mb-6">
      <HammerIcon class="w-6 h-6" /> Promptsmith
    </h1>

    <NuxtLink to="/forge" class="inline-flex items-center gap-2 bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700">
      <PlusIcon class="w-4 h-4" /> Forge New Prompt
    </NuxtLink>

    <div class="grid gap-4 mt-6">
      <PromptCard
        v-for="prompt in samplePrompts"
        :key="prompt.id"
        :title="prompt.title"
        :description="prompt.description"
        :model="prompt.model"
        :last-edited="prompt.lastEdited"
        :link="`/edit/${prompt.id}`"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { HammerIcon, PlusIcon } from 'lucide-vue-next'
import PromptCard from '@/components/PromptCard.vue'

const samplePrompts = [
  {
    id: '1',
    title: 'Code Explainer',
    description: 'Explains complex code in simple terms',
    model: 'GPT-4',
    lastEdited: '2 days ago',
  },
  {
    id: '2',
    title: 'SQL Query Generator',
    description: 'Generates SQL queries from natural language',
    model: 'Claude 3',
    lastEdited: '5 hours ago',
  },
  {
    id: '3',
    title: 'Bug Fixer',
    description: 'Identifies and fixes bugs in code snippets',
    model: 'GPT-4',
    lastEdited: '1 week ago',
  },
  {
    id: '4',
    title: 'Documentation Writer',
    description: 'Creates documentation from code comments',
    model: 'Claude 3',
    lastEdited: '3 days ago',
  },
  {
    id: '5',
    title: 'API Design Assistant',
    description: 'Helps design RESTful APIs',
    model: 'GPT-4',
    lastEdited: '2 days ago',
  },
]
</script>
