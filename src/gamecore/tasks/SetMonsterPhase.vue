<script setup lang="ts">
  import { GamecoreTask, GamecoreTargetType, } from '@/sources/gamecore';
  import BlockLayout from '@/components/BlockLayout.vue';
  import EvaluateTargetType from '../EvaluateTargetType.vue';

  const props = defineProps<{node:GamecoreTask}>()
  const node = props.node as unknown as 
  {
    TargetType?:GamecoreTargetType
    PhaseNum?:number
  }
</script>

<template>
  <BlockLayout :source="node">
    
    Change 
    <template v-if="node.TargetType">
      <em><EvaluateTargetType :target="node.TargetType" /></em>'s 
    </template>
    <template v-else>
      monster's 
    </template>
    phase to <em>{{ node.PhaseNum ?? 1 }}</em>

  </BlockLayout>
</template>

<style scoped>
</style>