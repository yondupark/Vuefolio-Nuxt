<template>
  <div>
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
          <button class="button contact" @click="modal = true;">Contact</button>
        </div>
      </nav>



      <div
        class="dialog"
        aria-labelledby="dialog_title"
        aria-describedby="dialog_description"
        v-if="modal == true"
      >
      <div>
          <h1 id="dialog_title" class="h2">How to Contact</h1>
          <div id="dialog_description">
              <p>이름 : 박상완</p>
              <p>메일 : <a href="mailto:sawa35@naver.com">sawa35@naver.com</a></p>
              <div>
                <a class="button file" href="https://firebasestorage.googleapis.com/v0/b/swvuefolio.appspot.com/o/resume.docx?alt=media&token=3a40057e-4345-43c2-a271-a58f506641fa" target="_blank">이력서/경력기술서 다운로드</a>
              </div>
          </div>
          <div class="flex center">
            <button id="confirm_dialog" class="cta" @click="modal = false;">Close</button>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
  export default {
    name: 'HeaderComp',
    data() {
      return {
        modal : false,
      }
    }
  }
</script>