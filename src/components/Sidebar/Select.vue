<template>
  <div :class="{arrow_active:dropdown_status}" class="sidebar__content__select">
        <span class="sidebar__content__select__title "
              @click="dropdown_handler">{{ name }}</span>
    <slot>

    </slot>


  </div>
</template>

<script>
export default {
  name: "Select",
  data() {
    return {
      dropdown_status: false
    };
  },
  mounted() {
    console.log(this.items[0].path);
  },
  props: {
    name: {
      type: String,
      required: true
    },
    items: {
      type: Array,
      required: true
    }

  },

  methods: {
    dropdown_handler() {
      this.dropdown_status = !this.dropdown_status;
    }
  }
};
</script>

<style scoped>

</style>
