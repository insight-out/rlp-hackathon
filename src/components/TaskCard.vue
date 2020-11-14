<template>
  <div v-if="visible" class="bg-white shadow rounded px-3 pt-3 pb-5 border border-white">
    <div class="flex justify-between">
      <p class="text-gray-700 font-semibold font-sans tracking-wide text-sm">
        {{ task.title }}
      </p>

      <div class="flex">
        <button
          aria-label="Edit user"
          class="action-button p-1 focus:outline-none focus:shadow-outline text-teal-500 hover:text-teal-600"
          @click="$emit('on-edit', user)"
        >
          <EditIcon size="15" />
        </button>
        <button
          aria-label="Delete user"
          class="action-button p-1 focus:outline-none focus:shadow-outline text-red-500 hover:text-red-600"
          @click="hide"
        >
          <Trash2Icon size="15" />
        </button>
      </div>
    </div>
    <!-- <div class="flex mt-4 justify-between items-center">
      <span class="text-sm text-gray-600">{{task.date}}</span>
      <badge v-if="task.type" :color="badgeColor">{{task.type}}</badge>
    </div> -->
  </div>
</template>
<script>
import { EditIcon, Trash2Icon } from "vue-feather-icons";
export default {
  components: {
    EditIcon,
    Trash2Icon,
  },
  data () {
    return {
      visible: true
    }
  },
  props: {
    task: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    badgeColor() {
      const mappings = {
        Design: "purple",
        "Feature Request": "teal",
        Backend: "blue",
        QA: "green",
        default: "teal",
      };
      return mappings[this.task.type] || mappings.default;
    },
  },
  methods: {
    hide () {
      this.$emit('remove')
    }
  }
};
</script>
