<template>
  <Layout>
    <template #header>
      <Header></Header>
    </template>
    <template #resume>
      <Resume :total-label="'Ahorro total'" :label="label" :total-amount="1200000" :amount="amount">
      <template #graphic>
        graphic
      </template>
      <template #action>
        action
      </template>
      </Resume>
    </template>
    <template #movements>
      <Movements
        :movements="movements"
      />
    </template>
  </Layout>
</template>

<script>
import Layout from "./Layout.vue";
import Header from "./Header.vue";
import Resume from "./Resume/Index.vue";
import Movements from "./Movements/Index.vue";

export default {
  components: {
    Layout,
    Header,
    Resume,
    Movements
  },
  data() {
    return {
      label: null,
      amount: null,
      movements: [
        {
          id: 1,
          title: "Movimiento",
          description: "Deposito de salario",
          amount: "1000",
        },
        {
          id: 2,
          title: "Movimiento 1",
          description: "Deposito de honorarios",
          amount: "500",
        },
        {
          id: 3,
          title: "Movimiento 3",
          description: "Comida",
          amount: "-100",
        },
        {
          id: 4,
          title: "Movimiento 4",
          description: "Colegiatura",
          amount: "1000",
        },
        {
          id: 5,
          title: "Movimiento 5",
          description: "Reparación equipo",
          amount: "1000",
        },
        {
          id: 6,
          title: "Movimiento 6",
          description: "Reparación equipo",
          amount: "1000",
        },
        {
          id: 7,
          title: "Movimiento 7",
          description: "Reparación equipo",
          amount: "1000",
        },
        {
          id: 8,
          title: "Movimiento 8",
          description: "Reparación equipo",
          amount: "1000",
        },
        {
          id: 9,
          title: "Movimiento 9",
          description: "Reparación equipo",
          amount: "1000",
        },
      ]
    }
  }
};

</script>