<template>
<div class="todos">
  <ToDo />
</div>
</template>

<script>
import ToDo from '@/components/ToDo.vue';


export default {
  name: 'App',
  components: {
    ToDo,
  }
}
</script>

<style>
/* .todos{
  display: flex;
  justify-content: center;
} */
</style>
