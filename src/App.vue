<template>
  <div class="container">
  <div class="row">
    <div class="col-12 mt-5 px-5">
      <h2 class="text-center">Services</h2>
      <div v-for="lesson in lessons" :key="lesson.id" :class="{ 'selected': lesson.isSelected }"
            @click="toggleActive(lesson)" 
           class="card mb-2">
        <div class="card-body">
          <div class="card-text">
            <span>{{ lesson.name }}</span>
            <span class="float-right">$ {{ lesson.price}}</span>            
          </div>
        </div>
      </div>
      <div class="total mb-5">
        <div class="arrow mb-2"></div>
        <span>Total : </span>
        <span class="float-right">$ {{ total() }}</span>

      </div>
      </div>
    </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      lessons: [
        { id: 1, name: 'Web Development', price: 300, isSelected: true },
        { id: 2, name: 'Network Administrator', price: 500, isSelected: false },
        { id: 3, name: 'Mobile Development', price: 250, isSelected: true },
      ],
      sumTotal: 0,
    }
  },
  computed: {

  },
  methods: {
    toggleActive(lesson) {
      lesson.isSelected = !lesson.isSelected;
    },
    total() {
      var total = 0;
      this.lessons.forEach(lesson => {
        if (lesson.isSelected) {
          total += lesson.price;
        }
      });

      return total;

    }
  }
}
</script>

<style scoped>
  .container {
  background-color: #61a1bc;
}

h2 { color: white; }

.card {
  background-color: #e35885;
  color: white;
  font-weight:bold;
  font-size:20px;
}

.selected {
  background-color:yellow;
  color:black;
}

.total {
  color:white;
  font-weight:bold;
  font-size:20px;
}

.arrow {
  border: 1px solid white;
}

</style>
