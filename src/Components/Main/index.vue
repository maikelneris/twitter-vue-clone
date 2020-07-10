<template>
  <div class="container">
    <div class="header">
      <div class="back-button">
        <ArrowLeftIcon :size="24" />
      </div>
      <div class="profile-info">
        <strong>Maikel Neris</strong>
        <span>840 Tweets</span>
      </div>
    </div>

    <ProfilePage />

    <Feed />

    <div class="bottom-menu">
      <HomeIcon :size="31" class="active" />
      <SearchIcon :size="31" />
      <BellIcon :size="31" />
      <EmailIcon :size="31" />
    </div>
  </div>
</template>

<script>
import ArrowLeftIcon from "vue-material-design-icons/ArrowLeft";
import HomeIcon from "vue-material-design-icons/HomeOutline";
import BellIcon from "vue-material-design-icons/BellOutline";
import EmailIcon from "vue-material-design-icons/EmailOutline";
import SearchIcon from "vue-material-design-icons/Magnify";
import ProfilePage from "../ProfilePage";
import Feed from "../Feed";

export default {
  components: {
    ProfilePage,
    Feed,
    ArrowLeftIcon,
    HomeIcon,
    BellIcon,
    EmailIcon,
    SearchIcon
  }
};
</script>

<style lang="scss" scoped>
$largura: 601px;

.container {
  display: flex;
  flex-direction: column;
  width: #{"min(601px, 100%)"};
}

.header {
  z-index: 2;
  position: sticky;
  top: 0;
  background-color: var(--primary);
  display: flex;
  align-items: center;
  text-align: left;
  padding: 8px 0 9px 13px;
  border-bottom: 1px solid var(--outline);

  > .back-button {
    padding: 8px;
    border-radius: 50%;
    outline: 0;
    cursor: pointer;

    svg {
      fill: var(--twitter);
    }

    &:hover {
      background-color: var(--twitter-dark-hover);
    }
  }
}

.profile-info {
  margin-left: 17px;
  display: flex;
  flex-direction: column;

  > strong {
    font-size: 19px;
  }

  > span {
    font-size: 15px;
    color: var(--gray);
  }
}

.bottom-menu {
  position: fixed;
  bottom: 0;
  left: 0;
  z-index: 2;
  width: 100%;
  background-color: var(--primary);
  border-top: solid 1px var(--outline);
  display: flex;
  justify-content: space-between;
  padding: 8px #{"min(46px, max(10vw, 10px))"};

  svg {
    cursor: pointer;
    fill: var(--gray);

    &:hover {
      fill: var(--twitter);
    }
  }

  span.active svg {
    fill: var(--twitter);
  }
}

@media (min-width: 500px) {
  .container {
    border-left: 1px solid var(--outline);
    border-right: 1px solid var(--outline);
  }
  .bottom-menu {
    display: none;
  }
}
</style>
