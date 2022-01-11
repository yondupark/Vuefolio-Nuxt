<template>
  <div class="main">
    <div class="vueHome">
      <div>
        <div>
          <h2>
            Hello World!<br />
            I’m <span>S.W Park.</span>
          </h2>
          <div>
            <p>
              I worked since<br />
              <span id="count" class="highlight">0</span> days.
            </p>
            <p>
              It gotta be <span class="highlight">Fun</span>.<br />
              It gotta be <span class="highlight">Cool</span>.<br />
              and it gotta be <span class="highlight">Sexy</span>. too.
            </p>
          </div>
          <div class="main_links">
            <nuxt-link to="/Career" class="button link">Career</nuxt-link>
            <a
              class="button github"
              href="https://github.com/yondupark/Vuefolio-Nuxt"
              target="_blank"
              >Github</a
            >
            <a
              class="button figma"
              href="https://www.figma.com/file/7aZxc1H1u0QAb4Vu4jyScP/My-Porfolios?node-id=0%3A1"
              target="_blank"
              >Figma</a
            >
          </div>
        </div>
        <div>
          <img src="@/assets/images/bg_main.svg" alt="" />
        </div>
      </div>
    </div>

    <div class="portfolios">
      <div>
        <div class="title_desc">
          <h2>
            My recent<br />
            works
          </h2>
          <p>Feel free to check my works out .</p>
          <nuxt-link to="/Myworks" class="button viewmore3">
            <span class="__hidden"> viewmore </span>
          </nuxt-link>
        </div>
        <ul class="workslists">
          <li v-for="(listData, idx) in listdata.slice(0, 3)" :key="idx">
            <nuxt-link to="/Myworks/WorksDetail">
              <div class="image">
                <img :src="`${listData.Image}`" alt="" />
              </div>
              <div class="texts">
                <p class="title2">{{ listData.Title }}</p>
                <h3 class="title">{{ listData.From }}</h3>
              </div>
            </nuxt-link>
          </li>
        </ul>
      </div>
    </div>

    <div class="whatihave">
      <div>
        <div class="title_desc">
          <h2>
            What I have &amp;<br />
            Interests
          </h2>
        </div>

        <ul class="list">
          <li>
            <h3>Based On</h3>
            <ul>
              <li v-for="basedata in basedon" :key="basedata">
                {{ basedata }}
              </li>
            </ul>
          </li>

          <li>
            <h3>Tools</h3>
            <ul>
              <li v-for="toolsdata in tools" :key="toolsdata">
                {{ toolsdata }}
              </li>
            </ul>
          </li>

          <li>
            <h3>Interests</h3>
            <ul>
              <li v-for="Interestsdata in Interests" :key="Interestsdata">
                {{ Interestsdata }}
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </div>

    <div class="madeby">
      <div>
        <div class="title_desc">
          <h2>Made this website as following :</h2>
        </div>

        <ul class="list">
          <li>
            <div>
              <img src="@/assets/images/ico_follow02.png" alt="" />
            </div>
            Node.js
          </li>
          <li>
            <div>
              <img src="@/assets/images/ico_follow01.png" alt="" />
            </div>
            Vue-CLI
          </li>
          <li>
            <div>
              <img src="@/assets/images/ico_follow06.svg" alt="" />
            </div>
            Nuxt.js
          </li>
          <li>
            <div>
              <img src="@/assets/images/ico_follow03.svg" alt="" />
            </div>
            Scss / Sass
          </li>
          <li>
            <div>
              <img src="@/assets/images/ico_follow04.svg" alt="" />
            </div>
            Firebase
          </li>
          <li>
            <div>
              <img src="@/assets/images/ico_follow05.svg" alt="" />
            </div>
            Github
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import listData from '@/static/listdata.js'

export default {
  name: 'IndexPage',
  data() {
    return {
      listdata: listData,
      basedon: [
        'HTML5 / CSS3',
        'Responsive',
        'Web Accessibility',
        'Javascript',
        'Sass / Less',
        'Git / SVN',
      ],
      tools: ['VS Code', 'Photoshop', 'Zeplin', 'Figma', 'Adobe XD'],
      Interests: ['React / Vue', 'WebGL', '3D Modeling', 'Interaction'],
    }
  },
  head: {
    title: 'Home',
    hid: 'description',
    name: 'description',
    content: 'description'
  },
  mounted() {
    calcdays() // 마운트가 완료되면 날짜를 삽입
  },
}

function calcdays() {
  const dday = new Date('08 01, 2013').getTime()
  const today = new Date().getTime()
  const gap = today - dday
  const day = Math.ceil(gap / (1000 * 60 * 60 * 24))
  document.getElementById('count').innerHTML = day
}
</script>


<style lang="scss" scoped>
.vueHome {
  background: #f8feff;
  padding: 15.8rem 0 9.2rem;
  > div {
    @include flexbox;
    @include contentsWrap;
    justify-content: space-between;
    align-items: center;
    width: 102.5rem;
    text-align: left;
    padding: 0;
    h2 {
      margin-bottom: 1.6rem;
      font-size: 4rem;
      line-height: 100%;
      color: $textColor;
      span {
        color: $pointColor;
      }
    }
    p {
      font-size: 2.4rem;
      letter-spacing: -0.75px;
      line-height: 1.4;
      margin-bottom: 3.2rem;
      font-weight: 400;
      .highlight {
        color: $pointColor;
        font-weight: 700;
      }
    }
    #count {
      margin: 2rem 0;
    }
    .main_links {
      display: flex;
      align-items: center;
      a + a {
        margin-left: 1rem;
      }
    }
  }
  .tools {
    margin-bottom: 3.5rem;
    ul {
      @include flexbox;
      justify-content: space-between;
      text-align: center;
      list-style: none;
      li {
        position: relative;
        width: 33.333%;
        color: $textColor;
        font-size: 2.8rem;
        font-weight: bold;
      }
      li + li:before {
        content: '+';
        display: block;
        position: absolute;
        top: 50%;
        left: -1rem;
        color: $textColor;
        transform: translateY(-50%);
      }
    }
    img {
      display: block;
      height: 14rem;
      margin: 0 auto 2.5rem;
    }
  }
}

.whatihave {
  padding: 5.5rem 0;
  background: #f8feff;
  > div {
    @include contentsWrap;
    @include flexbox;
    width: 102.5rem;
    flex-direction: column;
    align-items: flex-start;
    padding: 0;
  }
  h2 {
    @include texttype1;
    text-align: left;
    font-weight: 700;
    font-size: 4rem;
    letter-spacing: -0.75px;
    line-height: 1;
  }
  .list {
    display: flex;
    width: 100%;
    list-style: none;
    h3 {
      font-size: 2.2rem;
      letter-spacing: -0.75px;
      margin-bottom: 1.5rem;
    }
    > li {
      color: $textColor;
      text-align: left;
      width: 30rem;
      font-size: 1.8rem;
    }
    > li + li {
      margin-left: 6.5rem;
    }
    ul {
      list-style: none;
    }
    ul li {
      position: relative;
      padding-left: 2rem;
    }
    ul li + li {
      margin-top: 0.7rem;
    }
    ul li:before {
      content: '';
      position: absolute;
      top: 8px;
      left: 0;
      display: block;
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: $textColor;
    }
  }
}

.madeby {
  padding: 5.5rem 0;
  > div {
    @include contentsWrap;
    @include flexbox;
    width: 102.5rem;
    flex-direction: column;
    align-items: flex-start;
    padding: 0;
  }
  h2 {
    @include texttype2;
    text-align: left;
    font-weight: 700;
    letter-spacing: -0.75px;
    line-height: 1;
  }
  ul {
    @include flexbox;
    width: 100%;
    list-style: none;
    justify-content: space-between;
    li {
      width: 10rem;
      font-size: 1.8rem;
      font-weight: 500;
    }
    li div {
      position: relative;
      height: 12rem;
      margin-bottom: 1.4rem;
    }
    li img {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      display: block;
      min-width: 70px;
    }
  }
}
.portfolios {
  .title_desc {
    font-size: 1.8rem;
  }
}
.workslists {
  margin-top: 2rem;
  justify-content: space-between;
  li {
    width: 30%;
    &:hover {
      position: relative;
      box-shadow: 0 0 10px 10px rgba(0, 0, 0, 0.3);
      transform: scale(1.1);
      z-index: 999;
    }
    .image {
      height: 20rem;
      img {
        display: block;
        position: relative;
        left: 50%;
        transform: translateX(-50%);
        height: auto;
        width: 100%;
      }
    }
  }
}
</style>
