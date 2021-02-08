<template>
  <p>
    Reaction Time - <span :class="rankColor">{{ score }}</span> ms
  </p>
  <p class="rank">{{ rankMsg }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rankMsg: null,
      rankColor: "",
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rankMsg = "Superman Fingers";
      this.rankColor = "superman";
    } else if (this.score < 400) {
      this.rankMsg = "Human Reflexes";
      this.rankColor = "human";
    } else {
      this.rankMsg = "Snail Pace...";
      this.rankColor = "snail";
    }
  },
};
</script>

<style>
p {
  margin-top: 50px;
}

.superman {
  font-weight: 600;
  color: rgb(29, 250, 0);
}

.human {
  font-weight: 600;
  color: rgb(250, 171, 0);
}

.snail {
  font-weight: 600;
  color: rgb(250, 0, 0);
}

.rank {
  margin-top: 20px;
  font-size: 1.4rem;
}
</style>
