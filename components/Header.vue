<template>
  <header>
    <nav id="nav" class="flexbox">
      <div class="logo">
        <nuxt-link to="/" class="logoico">
          <span class="__hidden">PortFolio</span>
        </nuxt-link>
      </div>
      <div class="menus">
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/Myworks">My Works</nuxt-link>
        <nuxt-link to="/Career">Career</nuxt-link>
        <nuxt-link to="/Review">Review</nuxt-link>
        <button class="button contact" @click="modal = true">Contact</button>
      </div>
    </nav>
    <div
      v-if="modal == true"
      class="dialog"
      aria-labelledby="dialog_title"
      aria-describedby="dialog_description"
    >
      <div>
        <h1 id="dialog_title" class="h2">How to Contact</h1>
        <div id="dialog_description">
          아래 파일을 다운로드하여 확인해주세요.
          <div>
            <a
              class="button file"
              href="https://firebasestorage.googleapis.com/v0/b/swvuefolio.appspot.com/o/resume.docx?alt=media&token=3a40057e-4345-43c2-a271-a58f506641fa"
              target="_blank"
              >이력서/경력기술서 다운로드</a
            >
          </div>
        </div>
        <div class="flex center">
          <button id="confirm_dialog" class="cta" @click="modal = false">
            Close
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp',
  data() {
    return {
      modal: false,
    }
  },
}
</script>

<style lang="scss" scoped>
#nav {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 99999;
  padding: 2rem;
  font-size: 1.6rem;
  box-shadow: 0px 7px 10px #dddddd;
  background: #fff;
  @include flexbox;
  a {
    display: block;
    margin: 0 1rem;
    padding: 1rem;
    color: $textColor;
    font-size: 1.8rem;
    font-weight: 500;
    text-decoration: none;
    &.router-link-exact-active {
      color: $pointColor;
    }
  }
  a.logoico {
    padding-left: 4.8rem;
    color: $pointColor;
    font-size: 2rem;
    font-weight: 700;
  }
  .menus {
    @include flexbox;
  }
  .button {
    margin-left: 2rem;
  }
}
.logoico {
  display: block;
  width: 7.9rem;
  height: 4.5rem;
  background: url(@/assets/images/logo.svg) no-repeat center center;
}

.dialog {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 99999;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  border: none !important;
  background: rgba(0, 0, 0, 0.3);
  animation: fadeIn 0.75s ease forwards;
  opacity: 0;
  @keyframes fadeIn {
    to {
      opacity: 1;
    }
  }
  > div {
    width: 100%;
    max-width: 60rem;
    background: #fff;
    padding: 2rem;
    border-radius: 1rem;
  }
  .h1 {
    font-size: 2.6rem;
    margin: 2rem 0 1rem;
    font-weight: 700;
  }
  .h2 {
    font-size: 2.2rem;
    margin: 2rem 0 1rem;
    font-weight: 500;
  }

  #dialog_description {
    font-size: 1.8rem;
    line-height: 1.625;
  }

  button {
    display: block;
    margin-top: 2rem;
    width: 16.5rem;
    height: 4.4rem;
    border-radius: 0.5rem;
    border: none;
    font-family: inherit;
    color: #fff;
    background-color: #ccc;
    font-size: 1.8rem;
    font-weight: 700;
    cursor: pointer;
  }

  button:focus {
    outline: none;
    border: 0.0625rem solid transparent;
    box-shadow: 0 0 0 0.125rem #fff, 0 0 0 0.2rem #333;
  }

  button.cta {
    background-color: #0ec8b9;
    color: white;
  }

  button.cta:focus {
    box-shadow: 0 0 0 0.125rem #fff, 0 0 0 0.2rem #333;
  }
  .flex {
    display: flex;
  }
  .flex.center {
    justify-content: center;
  }
  .button + .button {
    margin-top: 1rem;
    margin-left: 2rem;
  }
}
</style>