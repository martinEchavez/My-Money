<template>
  <div class="container">
    <div>
      <h4>{{ title }}</h4>
      <p>{{ description }}</p>
    </div>

    <div class="action">
      <img src="@/assets/edit-icon.svg" alt="Delete" width="32" @click="edit">
      <img src="@/assets/trash-icon.svg" alt="Delete" width="32" @click="remove">
      <p :class="{ red: isNegative, green: !isNegative }">{{ amountCurrency }}</p>
    </div>
  </div>
</template>

<script setup>
import { toRefs, defineProps, defineEmits, computed } from "vue";

const currencyFormater = new Intl.NumberFormat(("es-CO"), {
  style: "currency", currency: "COP"
})

const props = defineProps({
  id: {
    type: Number,
  },
  title: {
    type: String,
  },
  description: {
    type: String,
  },
  amount: {
    type: Number,
  },
});

const { id, title, description, amount } = toRefs(props);

const amountCurrency = computed(() => currencyFormater.format(amount.value));

const isNegative = computed(() => amount.value < 0);

const remove = () => {
  console.log(id.value);
}

const edit = () => {
  console.log(id.value);
}
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: auto auto;
  gap: 10px;
  padding: 10px;
  width: 100%;
  background-color: #e9e9e9;
  border-radius: 8px;
  box-sizing: border-box;
}

.action {
  text-align: right;
}

h4,
p {
  margin: 0;
  padding: 0;
}

h4 {
  margin-bottom: 8px;
}

.red {
  color: red;
}

.green {
  color: green;
}
</style>