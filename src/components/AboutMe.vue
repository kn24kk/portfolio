<template>
  <div id="aboutme" class="aboutme">
    <h2 class="title">About Me</h2>
    <div class="container">
      <table class="list">
        <tr v-for="item in profile" class="item">
          <th class="name">{{ item.title }}</th>
          <td>{{ item.data }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AboutMe',
  data() {
    return {
      profile: [
        {title:'氏名',data:'神津薫'},
        {title:'スキル',data:'HTML5, CSS3, SASS, JavaScript, jQuery, Vue, Git, PhotoShop, Illustrator, Visual Studio Code'},
        {title:'実務経験があるもの',data:'企業ページ, LPページ, バナー, メールマガジン, 小規模なWebサイトのディレクション, CMS（MovableType）の組み込み、エンドユーザー向けマニュアルライティング'},
        {title:'得意な作業',data:'コーディング'},
        {title:'今後目指すもの',data:'エンドユーザーから社内スタッフまで、多方面のWebサービス利用者が快適に使用するためのUXデザインをする'},
      ]
    }
  },
  methods: {
  }
}
</script>

<style scoped lang="scss">
@import '../ver.scss';

.aboutme {
  padding: 4em 0;
  background: darken($color: $l-gray, $amount: 5);
  background: linear-gradient(45deg, $l-gray, darken($l-gray,10));
}
.container {
  margin: 0 8vw;
}
.title {
  @include title;
  margin-bottom: 2em;
  text-align: center;
}
.list {
  width: 80vw;
  margin: 0 auto;
  text-align: left;
  th {
    width: 30%;
  }
  th, td {
    padding: .5em;
    border-bottom: 1px solid #fff;
    line-height: 1.8;
  }
}

</style>