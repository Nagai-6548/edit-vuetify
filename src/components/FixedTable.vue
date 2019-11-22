<template>
  <v-data-table
    v-model="selected"
    :headers="headers"
    :items="recs"
    :single-select="singleSelect"
    :items-per-page="100"
    :fixed-header="true"
    :height="500"
    item-key="name"
    show-select
  >
    <template v-slot:top>
      <v-switch v-model="singleSelect" label="Single select" class="pa-3"></v-switch>
    </template>
  </v-data-table>
</template>

<script>
export default {
  name: 'FixedTable',
  data: () => ({
    singleSelect: false,
    recs: [],
    headers: [
      { text: 'Name', value: 'name' },
      { text: 'Number', value: 'number' },
      { text: 'Color', value: 'color' }
    ],
    selected: []
  }),
  mounted() {
    let colors = ["#ff6347", "#4169e1", "#32cd32"]
    for (let i = 1; i <= 500; i++) {
      let num = Math.random() * 100 + 100
      this.recs.push({
        name: `name${String(i).padStart(3, "0")}`,
        number: num,
        color: colors[num > 150 ? 0 : num > 120 ? 1 : 2]
      })
    }
  }
};
</script>
