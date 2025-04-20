<template>
  <BreadCrumbs :name="project?.name ?? 'No name'" />
</template>

<script lang="ts" setup>
import BreadCrumbs from '@/modules/common/components/BreadCrumbs.vue';
import { useProjectsStore } from '../store/projects.store';
import { computed } from 'vue';

interface Props {
  id: string;
}

const props = defineProps<Props>();
const projectStore = useProjectsStore();

const project = computed(() =>
  projectStore.projectList.find((project) => project?.id === props.id),
);
</script>
