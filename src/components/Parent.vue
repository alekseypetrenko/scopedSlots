<template>
  <div class="parentsssss">
    <h2>{{ title }}</h2>
    <Child>
      <template v-for="(index, name) in $scopedSlots" v-slot:[name]="data">
        <slot :name="name" v-bind="data"></slot>
      </template>
    </Child>
  </div>
</template>

<script>
import Child from "./Child.vue";

export default {
  name: "Parent",
  props: ["title"],
  components: {
    Child,
  },
  methods: {},
  created() {
    console.log(this.$slots);
  },
};
</script>

<style>
</style>