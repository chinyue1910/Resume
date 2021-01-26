<template lang="pug">
#home
  #section01
    #job.section01(v-if="show") Frontend Engineer
    #name.section01 Chin Yue Chuang
    #description.section01 踏入前端工程將近一年的經歷
  #section02
    .title About Me
    b-container
      b-row
        b-col.d-flex.flex-column.justify-content-around.bg-dark.text-white.p-3(
          cols="12",
          md="6"
        )
          .profile 莊欽淯
          .profile Frontend Engineer
          .profile New Taipei City，TW
          .link
            a(href="#")
              font-awesome-icon(:icon="['fas', 'envelope']")
              | Email
            a(href="#")
              font-awesome-icon(:icon="['fab', 'github']")
              | Github
        b-col.p-3(cols="12", md="6")
          .graph
            p 我有將近一年的網頁開發經驗
            p 對我來說，寫程式是用來解決生活的問題
            p 所以我很樂於挑戰，也很樂於學習新技能
            p 目前正朝著前端網頁工程師的目標繼續前進中
            p 應用所學的知識做出符合現今網頁規格及具有商業概念的網頁
  #section03
    .title Skill
    b-container
      b-row.justify-content-around
        b-col.py-3(cols="12", lg="3")
          h2 視覺傳達設計
          ul
            li Photoshop
            li Illustrator
            li Figma
        b-col.py-3(cols="12", lg="3")
          h2 前端網頁技術
          ul
            li HTML
            li CSS
            li JavaScript
            li Bootstrap
            li jQuery
            li Vue.js
            li Vue Cli
            li Nuxt.js
            li SASS
        b-col.py-3(cols="12", lg="3")
          h2 後端程式開發
          ul
            li Node.js
            li MongoDB
            li RESTful API
            li C++
  #section04
    .title My Resume
    b-container
      h2 職業訓練
      .resume
        h4 前端網頁開發技術
        h6 2020 年 2 月 - 2020 年 8 月
        h5 泰山職業訓練場
        p 參加 936 小時的職前訓練，習得前端網頁開發的技術，包含基本的 HTML、CSS 及 JavaScript，能使用 Bootstrap、jQuery、Vue.js、Node.js 及 MongoDB 進行網頁建置，透過 RESTful API 串接資料及利用 Git 版本控制管理專案，擅長使用 Vue Cli 以及 Nuxt.js 獨立架設專案網頁，並且在課程最後取得第一名結訓。
      h2 學業經歷
      .resume
        h4 應用物理學系
        h6 2012 年 9 月 - 2016 年 6 月
        h5 國立高雄大學
        p 擔任班代，綜理班級管理相關事務，傳達並執行學校及導師交辦事項。
        p.m-0 擔任系學會公關，主責項目如下：
        ul.pl-3
          li 活動事前至事後，負責接待師長與貴賓
          li 負責系上活動之行動宣傳
          li 促進系會與其他社團的交流
          li 找尋活動贊助商
      h2 工作經歷
      .resume
        h4 前端工程師
        h6 2020 年 9 月 - 至今
        h5 視覺力有限公司
        p 在公司擔任前端網頁工程師一職，與視覺設計師、後端工程師合作，開發前端互動功能，並且開發各項 Adobe extension
  #section05
    .title Portfolio
    b-container
      b-row
        b-col(cols="12" md="6" xl="4", v-for="(card, index) in cards", :key="index").pb-5
          .carditem
            .cardtitle {{ card.title }}
            b-img(
              fluid,
              :src="card.src"
            )
            .cardbody
              h6 {{ card.text.tools }}
              ul.px-3
                li(v-for="(feature, index) in card.text.features", :key="index") {{ feature }}
            .cardfooter
              b-link(:href="card.github")
                font-awesome-icon(:icon="['fab', 'github']")
              b-link(:href="card.web")
                font-awesome-icon(:icon="['fas', 'globe']")
  #section06
    h6.text-center Copyright &copy; 2020 Chin-Yue Chuang. All rights reserved.
</template>

<script>
export default {
  data () {
    return {
      show: false,
      cards: [
        {
          src:
            'https://camo.githubusercontent.com/2cd4fde91121115118d422cd29e38910e8448392/68747470733a2f2f692e696d6775722e636f6d2f677746756479762e6a7067',
          title: '映筑香菇農場',
          text: {
            tools:
              '藉由 Vue Cli 開發環境，結合後端及資料庫 MongoDB 獨立架設的電商平台',
            features: [
              '註冊/登入會員',
              '支援第三方註冊登入 Facebook',
              '簡易操作的後台管理系統',
              '購物車及送出訂單功能',
              '支援PWA'
            ]
          },
          github: 'https://github.com/chinyue1910/yingju',
          web: 'https://chinyue1910.github.io/yingju/#/'
        },
        {
          src:
            'https://camo.githubusercontent.com/ef820f66a606c2f874a724023de4daeb4475f3ff/68747470733a2f2f692e696d6775722e636f6d2f737573744f34392e706e67',
          title: '番茄鐘',
          text: {
            tools:
              '藉由 Nuxt.js 搭配 heroku 以完成 SSR 開發環境',
            features: [
              '可新增/刪除代辦事項',
              '工作/休息時間可自定義',
              '提供三種鬧鈴可自行選擇',
              '支援PWA'
            ]
          },
          github: 'https://github.com/chinyue1910/nuxtpomodoros',
          web: 'https://nuxtpomodoros.herokuapp.com/'
        },
        {
          src:
            'https://camo.githubusercontent.com/277367d5e990680650353b53b3aed41afc004dd9/68747470733a2f2f692e696d6775722e636f6d2f716c6b473855752e6a7067',
          title: 'Youtube 影音平台',
          text: {
            tools:
              '串接 Youtube API，並且利用 Video.js 播放 m3u8 格式影片',
            features: [
              '可新增/刪除收藏喜歡的影片',
              '支援RWD'
            ]
          },
          github: 'https://github.com/chinyue1910/youtubeVideo',
          web: 'https://chinyue1910.github.io/youtubeVideo/#/'
        },
        {
          src:
            'https://camo.githubusercontent.com/d0111cdb796ae3ccc98fc8eaee701b5ca8458c06/68747470733a2f2f692e696d6775722e636f6d2f51746d4c636a442e6a7067',
          title: '零壹科技',
          text: {
            tools:
              '企業活動一頁式網頁製作',
            features: [
              '依要求規劃RWD',
              '根據 Prototype 刻出要求的功能'
            ]
          },
          github: 'https://github.com/chinyue1910/daydreamLab',
          web: 'https://chinyue1910.github.io/daydreamLab/'
        },
        {
          src:
            'https://camo.githubusercontent.com/03d912f0000b497d2b4c20e875dad99300797459/68747470733a2f2f692e696d6775722e636f6d2f766f6b383837462e6a7067',
          title: '夾娃娃機',
          text: {
            tools:
              '使用 jQuery 製作出夾娃娃機小遊戲',
            features: [
              '操作方式以左、右鍵控制方向，空白鍵夾取',
              '可再夾取過程中快速夾取',
              '使用技術：jQuery'
            ]
          },
          github: 'https://github.com/chinyue1910/-Claw_machine',
          web: 'https://chinyue1910.github.io/-Claw_machine/homework.html'
        },
        {
          src:
            'https://camo.githubusercontent.com/c2fa37906de3108e9bfcf25a58e5cb6b083e96f0/68747470733a2f2f692e696d6775722e636f6d2f4d6773365844732e6a7067',
          title: '古典時鐘',
          text: {
            tools:
              '使用原生 javascript 及繪圖軟體製作出古典時鐘',
            features: [
              '使用技術：Javascript',
              '繪圖軟體：photoshop'
            ]
          },
          github: 'https://github.com/chinyue1910/-Claw_machine',
          web: 'https://chinyue1910.github.io/-Claw_machine/homework.html'
        },
        {
          src:
            'https://camo.githubusercontent.com/85a761281c8e19066a9294197086c91c68909fe9/68747470733a2f2f692e696d6775722e636f6d2f713175415837352e706e67',
          title: 'KKBox Linebot',
          text: {
            tools:
              '串接 KKBox 以及 Youtube API，輸入指令簡易查詢到自己想要的歌曲',
            features: [
              'line 好友搜尋 @052emheh',
              '"rank" 查詢各大榜單',
              '"!<歌曲名稱>" 查詢相關結果',
              '"@<歌手名稱>" 查詢歌手 Top 歌曲'
            ]
          },
          github: 'https://github.com/chinyue1910/line',
          web: 'https://github.com/chinyue1910/line'
        }
      ]
    }
  },
  mounted () {
    setTimeout(() => {
      this.show = true
    }, 1000)
  }
}
</script>

<style lang="scss" scoped>
@mixin sm {
  @media (min-width: 576px) {
    @content;
  }
}
@mixin md {
  @media (min-width: 768px) {
    @content;
  }
}
@mixin lg {
  @media (min-width: 992px) {
    @content;
  }
}

#section01 {
  background: url("https://picsum.photos/1920/1080/?random=1") no-repeat fixed
    center/cover;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  @include md {
    align-items: flex-start;
  }
  &::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    backdrop-filter: brightness(50%);
    z-index: 0;
  }
  .section01 {
    color: white;
    z-index: 1;
    @include md {
      padding-left: 5rem;
    }
  }
  #job {
    font-weight: bolder;
    font-size: 2.5rem;
    margin-bottom: 2rem;
    @include sm {
      font-size: 3.5rem;
    }
    @include md {
      font-size: 4.5rem;
    }
  }

  #name {
    font-size: 2rem;
    font-weight: bold;
    @include sm {
      font-size: 3rem;
    }
    @include sm {
      font-size: 3.5rem;
    }
  }

  #description {
    font-size: 1rem;
    margin: 1rem 0;
    letter-spacing: 2rem;
  }
}

#section02 {
  padding: 100px 0;
  overflow: hidden;
  .title {
    font-size: 3rem;
    font-weight: bolder;
    text-align: center;
    position: relative;
    letter-spacing: 1rem;
    margin: 1rem 0;
    &::before {
      position: absolute;
      content: "About Me";
      width: 150%;
      height: 150%;
      left: 50%;
      top: 0;
      font-size: 4rem;
      font-weight: bolder;
      color: rgba(0, 0, 0, 0.1);
      transform: translate(-50%, -50%);
      z-index: 9;
    }
  }
  .profile {
    font-size: 1.5rem;
    text-indent: 3rem;
    position: relative;
    font-weight: bolder;
    &::before {
      content: "";
      position: absolute;
      left: 0;
      top: 50%;
      width: 20px;
      height: 20px;
      border-radius: 50%;
      transform: translateY(-50%);
      background: linear-gradient(white 10%, grey 50%, black);
    }
    &::after {
      content: "";
      position: absolute;
      left: 4px;
      top: 50%;
      width: 12px;
      height: 12px;
      border-radius: 50%;
      transform: translateY(-50%);
      background: white;
    }
  }
  .link {
    display: flex;
    padding: 1rem 0;
    margin-left: auto;
    a {
      color: wheat;
      padding-right: 1rem;
      text-decoration: none;
      svg {
        margin-right: 5px;
      }
    }
  }
  .graph {
    font-weight: bolder;
  }
  .row {
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.1);
    position: relative;
    margin: 5rem 0;
    &::before {
      content: "";
      position: absolute;
      background: linear-gradient(
        30deg,
        white 20%,
        rgba(0, 0, 0, 0.1) 21%,
        transparent 21%
      );
      width: 50%;
      height: 100%;
      left: -50px;
      bottom: -50px;
      z-index: 9;
      pointer-events: none;
    }
    &::after {
      content: "";
      position: absolute;
      background: linear-gradient(
        210deg,
        white 20%,
        rgba(0, 0, 0, 0.1) 21%,
        transparent 21%
      );
      width: 50%;
      height: 100%;
      right: -50px;
      top: -50px;
      pointer-events: none;
    }
  }
}
#section03 {
  background-color: #eee;
  overflow: hidden;
  padding: 100px 0;
  .title {
    font-size: 3rem;
    font-weight: bolder;
    text-align: center;
    position: relative;
    margin: 1rem 0;
    letter-spacing: 2rem;
    &::before {
      position: absolute;
      content: "Skill";
      width: 150%;
      height: 150%;
      left: 50%;
      top: 0;
      font-size: 4rem;
      font-weight: bolder;
      color: rgba(0, 0, 0, 0.1);
      transform: translate(-50%, -50%);
      z-index: 9;
    }
  }
  h2 {
    font-weight: bolder;
    text-align: center;
    text-shadow: 5px 5px 5px rgba(0, 0, 0, 0.1);
    filter: drop-shadow(0 0 1px white);
  }
  ul {
    list-style-image: url("~@/assets/images/pen.png");
    padding-left: 40%;
    @include lg {
      padding: 0;
    }
    li {
      font-size: 1.5rem;
      font-style: italic;
    }
  }
}

#section04 {
  overflow: hidden;
  padding: 100px 0;
  .title {
    font-size: 3rem;
    font-weight: bolder;
    text-align: center;
    position: relative;
    margin: 1rem 0;
    letter-spacing: 1rem;
    &::before {
      position: absolute;
      content: "My Resume";
      width: 150%;
      height: 150%;
      left: 50%;
      top: 0;
      font-size: 4rem;
      font-weight: bolder;
      color: rgba(0, 0, 0, 0.1);
      transform: translate(-50%, -50%);
      z-index: 9;
    }
  }
  .resume {
    position: relative;
    padding: 0 2rem;
    margin: 2rem 0;
    &::before {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 100%;
      height: calc(100% - 1rem);
      border-left: 2px solid black;
      transform: translateX(-1px);
    }
    &::after {
      content: "";
      position: absolute;
      left: 0;
      top: 15px;
      width: 15px;
      height: 15px;
      border: 1px solid black;
      background-color: white;
      border-radius: 50%;
      transform: translate(-50%, -50%);
    }
  }
  h2 {
    font-weight: bolder;
    text-shadow: 0 0 1px black;
    filter: drop-shadow(0 0 1px white);
  }
  h4 {
    color: gold;
    font-weight: bolder;
    margin-bottom: 1rem;
    text-shadow: 1px 1px 1px black;
  }
  h6 {
    background: linear-gradient(90deg, rgba(0, 0, 0, 0.1), transparent 50%);
    font-weight: bolder;
    margin-bottom: 1rem;
  }

  h5 {
    font-style: italic;
    margin-bottom: 2rem;
  }

  p {
    text-align: justify;
    font-weight: bold;
  }
  ul {
    font-weight: bold;
  }
}

#section05 {
  overflow: hidden;
  padding: 100px 0;
  .title {
    font-size: 3rem;
    font-weight: bolder;
    text-align: center;
    position: relative;
    margin: 1rem 0;
    letter-spacing: 1rem;
    &::before {
      position: absolute;
      content: "Portfolio";
      width: 150%;
      height: 150%;
      left: 50%;
      top: 0;
      font-size: 4rem;
      font-weight: bolder;
      color: rgba(0, 0, 0, 0.1);
      transform: translate(-50%, -50%);
      z-index: 9;
    }
  }
  .col-4 {
    min-height: 500px;
  }
  .carditem {
    background-color: white;
    min-height: 500px;
    position: relative;
    left: 0;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.6);
    transition: 0.5s;
    &:hover {
      box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
      transform: translateY(-5px);
    }
    img{
      margin-bottom: 1rem;
    }
    .cardtitle {
      font-size: 2rem;
      padding: 0.5rem 1rem;
      color: rgba(0, 0, 0, 0.6);
      font-weight: 500;
    }
    .cardbody {
      padding: 0.5rem 1rem;
      h6 {
        font-weight: bold;
        text-align: justify;
        min-height: 4rem;
      }
    }
    .cardfooter {
      position: absolute;
      display: flex;
      bottom: -26px;
      right: 50%;
      width: 50%;
      transform: translateX(50%);
      justify-content: space-around;
      a{
        flex: 0 0 40%;
        text-align: center;
        background:linear-gradient(rgb(230,230,230),1%,white 5%,rgb(125,125,125) 50%,black);
        padding: 0.5rem;
        font-size: 1.5rem;
        color: white;
        border-radius: 1rem;
        box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.5);
        &:hover{
          background:linear-gradient(rgb(230,230,230),1%,white 5%,gold 50%,rgb(255, 80, 0));
        }
      }
    }
  }
}
#section06{
  padding: 1rem 0;
  background: black;
  color: white;
}
</style>
