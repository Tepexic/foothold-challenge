<template>
  <div class="h-screen w-full">
    <menu-button :open="open" @toggle-button="toggle" />
    <unicon name="car-wash" fill="limegreen"></unicon>
    <transition name="fade">
      <div
        class="absolute right-0 md:bottom-0 md:mb-20 p-6 grid gap-4 grid-cols-1 md:grid-cols-2 overflow-auto"
        v-show="open"
      >
        <menu-item
          v-for="m in menu"
          :key="m.name"
          :icon="m.icon"
          :description="m.name"
        />
      </div>
    </transition>
  </div>
</template>

<script>
import MenuButton from "@/components/MenuButton.vue";
import MenuItem from "@/components/MenuItem.vue";

export default {
  name: "App",
  data() {
    return {
      open: false,
      menu: [
        {
          icon: "new_intake.svg",
          name: "New intake",
        },
        {
          icon: "discharge.svg",
          name: "Discharge",
        },
        {
          icon: "checkin.svg",
          name: "Check in",
        },
        {
          icon: "checkout.svg",
          name: "Check out",
        },
        {
          icon: "pill.svg",
          name: "New medication",
        },
        {
          icon: "treatment.svg",
          name: "New treatment plan",
        },
        {
          icon: "bandage.svg",
          name: "New incident",
        },
        {
          icon: "calendar.svg",
          name: "New calendar event",
        },
        {
          icon: "progress.svg",
          name: "New progress note",
        },
        {
          icon: "note.svg",
          name: "New group note",
        },
      ],
    };
  },
  components: {
    MenuButton,
    MenuItem,
  },
  methods: {
    toggle() {
      this.open = !this.open;
    },
  },
};
</script>
MenuButton

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
