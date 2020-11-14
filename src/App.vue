<template>
  <div id="app">
    <Navbar />
    <h1>Standort Mainz</h1>
    <div class="flex justify-center">
      <div class="min-h-screen flex overflow-x-scroll py-12">
        <div
          v-for="column in columns"
          :key="column.title"
          class="rounded-lg px-3 py-3 column-width rounded mr-4"
          :class="getBgColor(column)"
        >
          <p
            class="text-gray-700 font-semibold font-sans tracking-wide text-sm"
          >
            {{ column.title }}
          </p>
          <!-- Draggable component comes from vuedraggable. It provides drag & drop functionality -->
          <draggable
            :list="column.tasks"
            :animation="200"
            ghost-class="ghost-card"
            group="tasks"
          >
            <!-- Each element from here will be draggable and animated. Note :key is very important here to be unique both for draggable and animations to be smooth & consistent. -->
            <task-card
              v-for="task in column.tasks"
              :key="task.id"
              :task="task"
              class="mt-3 cursor-move"
              @remove="removePerson(task)"
            ></task-card>
            <!-- </transition-group> -->
          </draggable>
        </div>
      </div>
    </div>
    <CTA @click="openModal" />
    <Modal
      v-show="showModal"
      @cancel="showModal = false"
      @submit="addPerson"
    />
  </div>
</template>

<script>
import draggable from "vuedraggable";
import TaskCard from "./components/TaskCard.vue";
import Navbar from "./components/Navbar.vue";
import CTA from "./components/CTA.vue";
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    TaskCard,
    Navbar,
    draggable,
    CTA,
    Modal,
  },
  data() {
    return {
      showModal: false,
      lastNr: 100,
      columns: [
        {
          title: "08:00 - 08:30",
          tasks: [
            {
              id: 1,
              title: "Weber, Pavel",
              date: "Sep 14",
              type: "Feature Request",
            },
            {
              id: 2,
              title: "Schmidt, Florian",
              date: "Sep 12",
            },
            {
              id: 5,
              title: "Rupprecht, Franca-A.",
              date: "Sep 12",
              type: "Backend",
            }
          ],
        },
        {
          title: "08:30 - 09:00",
          tasks: [
            {
              id: 3,
              title: "Streuber, Matthias",
              date: "Sep 9",
              type: "Design",
            },
            {
              id: 4,
              title: "Schneider, Andreas",
              date: "Sep 14",
              type: "Feature Request",
            }
          ],
        },
        {
          title: "09:00 - 09:30",
          tasks: [
            {
              id: 6,
              title: "Zeunert, Jonas",
              date: "Sep 12",
            },
          ],
        },
        {
          title: "09:30 - 10:00",
          tasks: [],
        },
        {
          title: "10:00 - 10:30",
          tasks: [],
        },
        {
          title: "10:30 - 11:00",
          tasks: [],
        },
        {
          title: "11:00 - 11:30",
          tasks: [],
        },
        {
          title: "11:30 - 12:00",
          tasks: [],
        },
      ],
    };
  },
  methods: {
    openModal () {
      this.showModal = true;
    },
    addPerson (person) {
      this.lastNr++
      this.columns[0].tasks.push({
        id: this.lastNr,
        title: `${person.lastName}, ${person.firstName}`
      })
    },
    getBgColor (column) {
      if (column.tasks.length > 3) {
        return 'bg-red-100'
      }
      return 'bg-gray-100'
    },
    removePerson (person) {
    }
  },
};
</script>

<style scoped>
.column-width {
  min-width: 320px;
  width: 320px;
}
/* Unfortunately @apply cannot be setup in codesandbox, 
but you'd use "@apply border opacity-50 border-blue-500 bg-gray-200" here */
.ghost-card {
  opacity: 0.5;
  background: #F7FAFC;
  border: 1px solid #4299e1;
}
h1 {
  font-size: 1.5rem;
  padding: 10px;
  margin-bottom: -30px;
}
</style>
