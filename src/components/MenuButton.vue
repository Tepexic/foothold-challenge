<template>
  <div
    class="rounded-full w-16 shadow-xl flex items-center justify-center fixed bottom-0 right-0 mr-4 mb-4 cursor-pointer z-40"
    :class="open ? 'bg-teal-900 p-3' : 'bg-teal-200 p-2'"
    @click="$emit('toggle-button')"
  >
    <transition name="fade">
      <svg
        v-if="open"
        class="text-teal-200"
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18L18 6M6 6l12 12"
        />
      </svg>
      <svg
        v-else
        class="text-teal-900"
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M12 6v6m0 0v6m0-6h6m-6 0H6"
        />
      </svg>
    </transition>
  </div>
</template>

<script>
export default {
  name: "MenuButton",
  props: {
    open: {
      type: Boolean,
      required: false,
      default: true,
    },
  },
};
</script>
