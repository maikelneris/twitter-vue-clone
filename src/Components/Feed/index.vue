<template>
  <div class="container">
    <div class="tab">Tweets</div>
    <div class="tweets">
      <Tweet
        retweet
        image
        name="Maikel Neris"
        profile="@maikelneris"
        time="27 de jun"
        comments="18"
        retweets="24"
        likes="48"
      >Foguete não tem ré</Tweet>
      <Tweet
        retweet
        image
        name="Denner Neris"
        profile="@denner"
        time="31 de jun"
        comments="18"
        likes="48"
      >Lorem Ipsun Dolor</Tweet>
    </div>
  </div>
</template>

<script>
import Tweet from "../Tweet";

export default {
  components: {
    Tweet
  }
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
}

.tab {
  margin-top: 10px;
  padding: 11px 0 15px;
  font-weight: bold;
  font-size: 15px;
  outline: 0;
  cursor: pointer;
  color: var(--twitter);
  border-bottom: solid 2px var(--twitter);
  text-align: center;

  &:hover {
    background: var(--twitter-dark-hover);
  }
}

.tweets {
  display: flex;
  flex-direction: column;
  flex-shrink: 0;
}
</style>