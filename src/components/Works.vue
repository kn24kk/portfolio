<template>
  <div id="works" class="works">
    <h2 class="title">Works</h2>
    <div class="container">
      <div class="list">
        <section v-for="(item, index) in works" class="item" v-on:click="open">
          <div class="images">
            <img v-bind:src="item.image" alt="" class="thumb">
          </div>
          <div class="body">
            <h3 class="name">{{ item.name }}</h3>
            <div class="date">{{ item.date }} / {{ item.org }}</div>
            <div class="tags">
              <span v-for="(tag) in item.tags" class="tag">
                {{tag}}
              </span>
            </div>
            <!--<button v-on:click="open" class="btn">詳細</button>-->
          </div>

          <div class="modal" :class="{'isActive': item.isActive}" :id="index">
            <div class="modal__body">
              <div class="modal__images">
                <img v-bind:src="item.image" alt="" class="modal__image">
              </div>
              <div class="modal__texts">
                <h4 class="modal__name">{{item.name}}</h4>
                <div class="modal__data">時期：{{item.date}} /  {{ item.org }}</div>
                <div class="modal__comment">{{item.comment}}</div>
                <div class="link" v-if="item.url"><a :href="item.url" rel="noreferrer noopener">{{item.url}}</a></div>
              </div>
            </div>
          </div>
          
        </section>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'Works',
  data() {
    return {
      works: [
        {name:'特集ページ',date:'2020年',org: '株式会社一休（派遣社員）',comment:'サイトのターゲット層である富裕層に対してアピールできるよう、施設の良さを生かしたページデザインとしました。このような特集ページを1週間に1本程度作成しました。作業時間は1本につき調査を含めおおよそ5時間〜10時間です。',image:'/images/img-ikyu01.png',tags:['画面デザイン','コーディング'],url: 'https://www.ikyu.com/dg01/tieup/2020/hulic_5/'},
        {name:'特集ページ',date:'2020年',org: '株式会社一休（派遣社員）',comment:'サイトのターゲット層である富裕層に対してアピールできるよう、施設の良さを生かしたページデザインとしました。このような特集ページを1週間に1本程度作成しました。作業時間は1本につき調査を含めおおよそ5時間〜10時間です。',image:'/images/img-ikyu01.png',tags:['画面デザイン','コーディング'],url: 'https://www.ikyu.com/dg01/tieup/2020/00002568/'},
        {name:'特集ページ',date:'2019年',org: '株式会社一休（派遣社員）',comment:'一つの施設に特化した特集ページのため、施設のコンセプトや公式サイトの雰囲気を継承したデザインとしました。',image:'/images/img-ikyu02.png',tags:['画面デザイン','コーディング'],url:'https://www.ikyu.com/dg01/tieup/2019/00000339/'},
        {name:'特集ページ',date:'2020年',org: '株式会社一休（派遣社員）',comment:'非日常的な雰囲気を演出するデザインとしました。',image:'/images/img-ikyu03.png',tags:['画面デザイン','コーディング'],url:'https://www.ikyu.com/dg01/special/fullyear/brand/00000616/'},
        {name:'検索結果ページ',date:'2019年',org: 'ヤフー株式会社（業務委託）',comment:'地域情報を検索するサイトでの検索結果画面のコーディングを担当しました。様々なブラウザでもデザイン画像を忠実に再現できるよう注意を払い作業にあたりました。',image:'/images/img-yahoo01.png',tags:['コーディング'],url:'https://loco.yahoo.co.jp/search/'},
        {name:'グルメマガジンサイト（作例）',date:'2019年',org: '作例',comment:'仮想のグルメウェブマガジンサイトのトップページを、Adobe XDを使用した作例として作成しました。',image:'/images/img-sample02.png',tags:['画面デザイン'],url:'https://xd.adobe.com/view/2f7052ec-ad42-42c9-b491-02e82dd4b592-7a23/?fullscreen'},
        {name:'求人サイト（作例）',date:'2019年',org: '作例',comment:'仮想の求人情報サイトのトップページを、Adobe XDを使用した作例として作成しました。主婦・主夫層がメインターゲットと想定し、近所から近い職場を探せるというコンセプトでデザインしました。',image:'/images/img-sample01.png',tags:['画面デザイン'],url:'https://xd.adobe.com/view/8c972ab7-4f28-4d0f-a3ff-5d5f2d381822-d9c4/?fullscreen'},
        {name:'サービス案内ページ',date:'2019年',org: 'スタイルアクト株式会社（パート）',comment:'「時間を節約できる」という訴求ポイントをアピールできるようなシンプルな雰囲気のデザインとしました。',image:'/images/img-sa01.png',tags:['画面デザイン','コーディング'],url:'https://www.sumai-surfin.com/service/premierChuko/'},
        {name:'キャンペーンページ',date:'2019年',org: 'スタイルアクト株式会社（パート）',comment:'春らしい雰囲気の明るいデザインとしました。',image:'/images/img-sa04.png',tags:['画面デザイン','コーディング'],url:'https://www.sumai-surfin.com/campaign/201903springcampaign/'},
        {name:'サービス紹介サイト',date:'2019年',org: 'スタイルアクト株式会社（パート）',comment:'困っていることに対しての解決策を提案できるというコンセプトで作成しました。サービスへのイメージがわきづらいという声もあり、トップページで「あるある」と思えるような事例を押し出しております。',image:'/images/img-sa03.png',tags:['サイト設計','画面デザイン','コーディング'],url:'https://www.stylerent.jp/'},
        {name:'特集ページ',date:'2019年',org: 'スタイルアクト株式会社（パート）',comment:'hogehogehogehoge',image:'/images/img-sa02.png',tags:['画面デザイン','コーディング'],url:'https://www.sumai-surfin.com/lab/stations-areas/bayside-cities/'},
        {name:'特集サイト',date:'2013年',org: '株式会社首都高（派遣社員）',comment:'レインボーブリッジ20周年を記念したサイトです。サイト設計からコーディングを担当、レインボーブリッジの橋脚をイメージしたロゴも作成しました。',image:'/images/img-shutoko02.jpg',tags:['サイト設計','画面デザイン','コーディング']},
        {name:'特集サイト',date:'2012年',org: '株式会社首都高（派遣社員）',comment:'首都高開通50周年を記念したサイトです。Facebook、Twitterの運用も提案し、更新も担当しました。',image:'/images/img-shutoko01.jpg',tags:['サイト設計','画面デザイン','コーディング']},
        {name:'特集サイト',date:'2011年',org: '日本情報システム株式会社（正社員）',comment:'受注前のヒアリングから納品までを担当、CMSとしてMovableTypeを使用しました。物件検索システムのUIデザインも担当しました。',image:'/images/img-njs01.jpg',tags:['サイト設計','画面デザイン','コーディング']},
        
      ]
    }
  },
  methods: {
    open: function(e) {
      //console.log(e.currentTarget.querySelector('.modal'))
      e.currentTarget.querySelector('.modal').classList.toggle('isActive')
      //var sample = document.getElementById('app')
      document.body.classList.toggle('modalOpen')
    },
    close: function(e) {
      //console.log(e.target.parentNode.classList)
      //e.target.parentNode.classList.toggle('isActive');
    }
  }
}
</script>

<style scoped lang="scss">
@import '../ver.scss';

#app {
  position: fixed;
}

.works {
  padding: 6em 0;
  background: linear-gradient(45deg, rgba(255, 255, 255, 0.6), rgba(255,255,255,0));
}
.title {
  @include title;
  margin-bottom: 2em;
  text-align: center;
}
.container {
  margin: 0 4vw;
}
.list {
  display: flex;
  margin: 0 auto;
  flex-wrap: wrap;
}
.item {
  width: calc((100% - 2vw) / 3);
  margin: 0 1vw 1vw 0;
  background: #fff;
  border-radius: 4px;
  overflow: hidden;
  cursor: pointer;
  &:nth-child(3n) {
    margin-right: 0;
  }
  :hover .thumb {
    filter: grayscale(0);
    opacity: 1;
    transform: scale(1.1);
    overflow: hidden;
  }
}
.body {
  padding: 2vw;
}
.name {
  margin-bottom: .5em;
}
.date {
  margin-bottom: 1em;
}
.tags {
  margin-bottom: 1em;
}
.tag {
  display: inline-block;
  margin-right: .2em;
  padding: .2em;
  font-size: 0.8em;
  color: #999;
  border: 1px solid #eee;
  border-radius: 4px;
}
.images {
  background: #000;
  line-height: 0;
  overflow: hidden;
}
.thumb {
  max-width: 100%;
  filter: grayscale(60%);
  opacity: .9;
  transition: .3s ease-in-out;
}
.modal {
  display: none;
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  background: rgba(70, 70, 70, 0.8);
  z-index: 200;
  
  &__body {
    margin: 10vh 10vw;
    background: white;
    border-radius: 4px;
    overflow: hidden;
  }
  &__images {
    height: 50vh;
    background: #222;
    text-align: center;
  }
  &__image {
    max-width: 100%;
    height: 50vh;
  }
  &__texts {
    height: 20vh;
    padding: 2vw;
    overflow: auto;
  }
  &__name {
    font-size: 1.2em;
    margin-bottom: .5em;
  }
  &__data {
    margin-bottom: 1em;
    color: $gray;
  }
  &__comment {
    margin-bottom: .5em;
    line-height: 1.8;
  }
}
.isActive {
  display: block;
}
</style>