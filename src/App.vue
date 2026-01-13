<script setup lang="ts">
import { reactive, ref } from 'vue';

const count = ref(0)

function reduceByTwo(event: Event) {
  count.value = count.value - 2;
}

function say(message: string) {
  alert(message);
}

</script>



<style scoped></style>
