<template>
  <div class="container">
    <div class="retweeted" v-if="retweet">Você retweetou</div>

    <div class="body">
      <div class="avatar"></div>
      <div class="content">
        <div class="header">
          <strong>{{name}}</strong>
          <span class="profile">{{profile}}</span>
          <span class="dot">&middot;</span>
          <time>{{time}}</time>
        </div>
        <p class="description">
          <slot />
        </p>
        <div class="image-content" v-if="image"></div>
        <div class="icons">
          <div class="status">
            <ChatIcon class="icon" :size="20" />
            {{comments}}
          </div>
          <div class="status">
            <RetweetIcon class="icon" :size="20" />
            {{retweets}}
          </div>
          <div class="status">
            <FavoriteIcon class="icon" :size="20" />
            {{likes}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ChatIcon from "vue-material-design-icons/ChatProcessingOutline";
import RetweetIcon from "vue-material-design-icons/TwitterRetweet";
import FavoriteIcon from "vue-material-design-icons/Heart";

export default {
  props: {
    retweet: Boolean,
    time: String,
    name: String,
    profile: String,
    image: Boolean,
    retweets: {
      value: Number,
      default: 0
    },
    likes: {
      value: Number,
      default: 0
    },
    comments: {
      value: Number,
      default: 0
    }
  },
  components: {
    ChatIcon,
    RetweetIcon,
    FavoriteIcon
  }
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  padding: 14px 16px;
  border-bottom: solid 1px var(--outline);
  max-width: 100%;
}

.retweeted {
  display: flex;
  align-items: center;
  font-size: 13px;
  color: var(--gray);
}

.body {
  display: flex;
  margin-top: 3px;
  position: relative;

  .avatar {
    width: 49px;
    height: 49px;
    border-radius: 50%;
    flex-shrink: 0;
    background: var(--gray);
    position: absolute;
    top: 0;
    left: 0;
  }
  .content {
    display: flex;
    flex-direction: column;
    width: 100%;
    margin-top: 2px;
    padding-left: 59px;

    .header {
      display: flex;
      align-items: center;
      font-size: 15px;
      white-space: nowrap;

      strong {
        margin-right: 5px;
      }

      span.profile,
      time {
        color: var(--gray);
      }

      strong,
      span.profile {
        white-space: nowrap;
        text-overflow: ellipsis;
        overflow: hidden;
      }

      span.dot {
        color: var(--gray);
        font-weight: bold;
        margin: 0 10px;
      }
    }
    .description {
      margin-top: 4px;
      font-size: 14px;
    }
    .image-content {
      margin-top: 12px;
      width: 100%;
      height: #{"min(285px, max(175px, 41vw))"};
      background: var(--outline);
      border-radius: 14px;
      cursor: pointer;

      &:hover {
        opacity: 0.7;
      }
    }
    .icons {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      margin: 9px auto 0;
      width: 100%;
      .status {
        display: flex;
        align-items: center;
        cursor: pointer;
        font-size: 14px;

        svg {
          margin-top: 5px;
          margin-right: 5px;
        }

        &:hover {
          opacity: 0.7;
        }
        &:nth-child(1) {
          color: var(--gray);
          svg {
            fill: var(--gray);
          }
        }
        &:nth-child(2) {
          color: var(--retweet);
          svg {
            fill: var(--retweet);
          }
        }
        &:nth-child(3) {
          color: var(--like);
          svg {
            fill: var(--like);
          }
        }
      }
    }
  }
}

@media (min-width: 330px) {
  .body {
    .content {
      .icons {
        width: 63%;
      }
    }
  }
}
</style>