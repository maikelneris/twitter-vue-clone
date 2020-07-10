<template>
  <div class="container">
    <div class="banner">
      <div class="avatar"></div>
    </div>

    <div class="profile-data">
      <Button class="profile-edit" outline>Editar perfil</Button>

      <h1>Maikel Neris</h1>
      <h2>@maikelneris</h2>

      <p>Desenvolvedor web apaixonado por novas tecnologias.</p>

      <ul>
        <li>
          <LocationIcon :size="20" />Rondonópolis, Brasil
        </li>
        <li>
          <CakeIcon :size="20" />Nascido em 12 de março de 1982
        </li>
      </ul>

      <div class="followage">
        <span>
          seguindo
          <strong>94</strong>
        </span>
        <span>
          <strong>346</strong> seguidores
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "../Button";
import LocationIcon from "vue-material-design-icons/MapMarker";
import CakeIcon from "vue-material-design-icons/CakeVariant";

export default {
  components: {
    Button,
    LocationIcon,
    CakeIcon
  }
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  max-height: 100%;
  overflow-y: auto;

  scrollbar-width: none;
  ::-webkit-scrollbar {
    display: none;
  }
}
.banner {
  flex-shrink: 0;
  width: 100%;
  height: #{"min(33vw, 199px)"};
  background: var(--twitter);
  position: relative;
}
.avatar {
  width: #{"max(45px, min(135px,22vw))"};
  height: #{"max(45px, min(135px,22vw))"};
  border: solid 3px var(--primary);
  background-color: var(--gray);
  position: absolute;
  border-radius: 50%;
  left: 7px;
  bottom: #{"max(-60px, -10vw)"};
}
.profile-data {
  padding: #{"min(calc(10vw + 7px),67px) 16px 0"};
  display: flex;
  flex-direction: column;
  position: relative;

  > h1 {
    font-weight: bold;
    font-size: 19px;
  }

  > h2 {
    font-weight: normal;
    font-size: 15px;
    color: var(--gray);
  }
  > p {
    font-size: 15px;
    margin-top: 11px;
  }

  a {
    text-decoration: none;
    color: var(--twitter);
  }

  ul {
    margin: 10px 0;
    li {
      display: flex;
      align-items: center;
      list-style-type: none;
      font-size: 15px;
      color: var(--gray);

      svg {
        fill: var(--gray);
        margin-right: 5px;
      }
    }
  }
}

.followage {
  display: flex;

  > span {
    font-size: 15px;
    color: var(--gray);

    & + span {
      margin-left: 20px;
    }
  }
}

.profile-edit {
  position: absolute;
  top: 2vw;
  right: 7px;
  padding: 4px 16px !important;
  font-size: 13px !important;
}

@media (min-width: 320px) {
  .profile-edit {
    top: 10px;
    padding: 10px 19px !important;
    font-size: 15px;
  }
}
</style>
