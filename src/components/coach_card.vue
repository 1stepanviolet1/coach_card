<template>
  <div class="coach-card">
    <hr>
    <div class="my-4 mx-3">
      <h1>Коуч по сбросу лишнего веса</h1>
    </div>
    <hr>
    <br>

    <div class="row row-cols-3">
      <img src="../assets/couch.jpg" alt="coach" class="coach-card" />
      <div>
        <h2 class="my-2">
          {{ coach_full_name }}
        </h2>
        <h6>Коуч</h6>
        <p>
          Научу сжигать жир килограммами в день!
          Сам я вешу около 170кг..
          Но это ничего не значит! Времени на себя просто не хватает..
          Сделаю из вас огурчика!
          Всего за 150 000р.
        </p>

      </div>
    </div>

  </div>
</template>

<script>

export default {
  name: 'CoachCard',

  data() {
    return {
      name: 'Иван',
      surname: 'Иванов'
    };
  },

  computed: {
    coach_full_name() {
      return `${this.name} ${this.surname}`.toUpperCase();
    }
  }
}

</script>

<style>

.coach-card {
  width: 66%;
}

</style>
