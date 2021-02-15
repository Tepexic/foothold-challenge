<template>
  <div
    class="rounded pl-6 pr-20 py-3 shadow-md hover:shadow-lg flex items-center justify-start"
  >
    <div class="h-12 w-12">
      <img class="object-cover w-full" :src="svgIcon" />
    </div>
    <p class="ml-4 md:ml-6">{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: "MenuItem",
  props: {
    icon: {
      type: String,
      required: false,
      default: "car-wash",
    },
    description: {
      type: String,
      required: true,
      default: "Menu item",
    },
  },
  computed: {
    svgIcon() {
      return require(`@/assets/svg/${this.icon}`);
    },
  },
};
</script>
