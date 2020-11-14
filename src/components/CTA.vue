<template>
  <div class="cta" @click="$emit('click')">
    <PlusIcon />
  </div>
</template>
<script>
import { PlusIcon } from "vue-feather-icons";
export default {
  components: { PlusIcon },
};
</script>
<style scoped>
.cta {
  position: fixed;
  bottom: 30px;
  right: 30px;
  padding: 10px;
  border-radius: 50px;
  color: white;
  background-color: #2D3748;
  box-shadow: 4px 4px 5px 0px rgba(50, 50, 50, 0.75);
  cursor: pointer;
}
</style>
