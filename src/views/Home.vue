<template>
  <div class="home">
    <v-img
      dark
      max-height="500px"
      src="../assets/mainVisual.jpg"
    >
      <v-layout fill-height align-center>
        <v-container>
          <v-row align="center" justify="center" class="white--text">
            <v-col cols="12">
              <div
                :class="{'display-2 font-weight-bold ': $vuetify.breakpoint.smAndUp, 'title font-weight-bold': $vuetify.breakpoint.smAndDown}"
              >Welcome to my page.</div>
              <div
                :class="{'headline': $vuetify.breakpoint.smAndUp, 'subtitle-1': $vuetify.breakpoint.smAndDown}"
              >I make applications.</div>
            </v-col>
          </v-row>
        </v-container>
      </v-layout>
    </v-img>
    <v-container class="mt-5">
      <v-layout wrap>
        <v-flex xs12>
          <div class="display-1 font-weight-bold" id="about">This is me</div>
        </v-flex>
        <v-flex xs12 mt-5>
          <div class="body-1" style="white-space:pre-line">{{aboutText}}</div>
          <div
            class="body-1 mt-3"
          >
          「エンジニアのチーム立ち上げ」や「事業のアイディアはあるが実現する手段が見つからない」という方、「アイディアの壁打ちをしたい」方など、お気軽に問い合わせください。
          </div>
        </v-flex>
      </v-layout>
      <v-layout wrap my-5>
        <v-flex xs12>
          <div class="display-1 font-weight-bold" id="portfolio">My Work</div>
        </v-flex>
        <v-flex xs12 class="mt-5">
          <v-layout wrap>
            <template v-for="(app, i) in apps">
              <v-flex :key="i" xs12 sm6 md4>
                <p-portfolio-app :app="app" style="white-space:pre-line" />
              </v-flex>
            </template>
          </v-layout>
        </v-flex>
      </v-layout>
      <v-layout wrap my-5>
        <v-flex xs12 mb-5>
          <div class="display-1 font-weight-bold" id="contact">Contact</div>
        </v-flex>
        <template v-for="(contact, i) in contactLinks">
          <v-flex sm6 md4 xs12 :key="i">
            <p-contact-info :contact="contact" />
          </v-flex>
        </template>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import PPortfolioApp from "@/components/PPortfolioApp.vue";
import PContactInfo from "@/components/PContactInfo.vue";

export default {
  name: "home",
  components: {
    PPortfolioApp,
    PContactInfo
  },
  data() {
    return {
      aboutText:
      `スタートアップにエンジニアとしてジョインしつつ、個人開発や新規事業の立ち上げにもジョインしています。\nエンジニアだけでなくマーケティング視点やアクター視点での開発を主に得意としています。\nエンジニアの教育事業にも興味があり、少しでもなりたい自分を実現できるような世の中に変わるように社会にコミットしていきます。`,
      apps: [
        {
          name: `人事・採用管理\nシステム`,
          logo: "human-resources.png",
          platforms: [{}],
          description:
          `企業の人事管理と評価や採用を一括でできるSaaSのサービスの開発に携わっていました。\n主にサーバーサイドエンジニアとしてAPI開発\nQAエンジニアとしてテスト要件の作成から結合テストまでを実施していました。\n \n`,
          url: "https://www.hitomawari.jp/",
          technologies: [
            {
              name: "Ruby",
              icon: "mdi-language-ruby",
              link: ""
            },
            {
              name: "Rails",
              icon: "mdi-language-ruby-on-rails",
              link: ""
            },
            {
              name: "Docker",
              icon: "mdi-docker",
              link: ""
            },
            {
              name: "AWS",
              icon: "mdi-aws",
              link: ""
            },
          ],
        },
        {
          name: `ベビシッター\nCtoCマッチング\nサービス`,
          logo: "baby.png",
          description:`訪問型ベビーシッターを求めるユーザーとベビーシッターのマッチングサービスプラットフォームの開発にサーバーサイドエンジニアとして参画していました。\n \n \n`,
          url: "https://kidsline.me/",
          technologies: [
            {
              name: "Ruby",
              icon: "mdi-language-ruby",
              link: ""
            },
            {
              name: "Rails",
              icon: "mdi-language-ruby-on-rails",
              link: ""
            },
            {
              name: "Docker",
              icon: "mdi-docker",
              link: ""
            },
            {
              name: "AWS",
              icon: "mdi-aws",
              link: ""
            }
          ],
        },
        {
          name: `法人不動産営業向け\n物件管理システム`,
          logo: "building.png",
          description:`法人向け不動産仲介会社で、社内の営業向けに既存の物件管理システムをリプレイスしました。\nエンジニアのチームビルディングやPMといった上流工程から実際の開発からテストまで包括的に携わりました。開発は基本的にはサーバーサイドの開発にコミットしていました。`,
          technologies: [
            {
              name: "Ruby",
              icon: "mdi-language-ruby",
              link: ""
            },
            {
              name: "Rails",
              icon: "mdi-language-ruby-on-rails",
              link: ""
            },
            {
              name: "Node.js",
              icon: "mdi-nodejs",
              link: ""
            },
            {
              name: "TypeScript",
              icon: "mdi-language-typescript",
              link: ""
            },
            {
              name: "Docker",
              icon: "mdi-docker",
              link: ""
            },
            {
              name: "AWS",
              icon: "mdi-aws",
              link: ""
            }
          ],
        },
        {
          name: `法人不動産営業向け\n物件提案システム`,
          logo: "sales.png",
          description:`法人向け不動産仲介会社で、社内向けの物件管理システムの追加システムとして開発しました。\n条件に合った物件情報をテナントに対して詳細資料と合わせて共有できるようなシステムを追加で開発し、営業の人的コスト削減と売り上げ貢献にコミットしました。\n \n`,
          technologies: [
            {
              name: "Node.js",
              icon: "mdi-nodejs",
              link: ""
            },
            {
              name: "TypeScript",
              icon: "mdi-language-typescript",
              link: ""
            },
            {
              name: "GraphQL",
              icon: "mdi-graphql",
              link: ""
            },
            {
              name: "React",
              icon: "mdi-react",
              link: ""
            },
            {
              name: "Docker",
              icon: "mdi-docker",
              link: ""
            },
            {
              name: "AWS",
              icon: "mdi-aws",
              link: ""
            }
          ],
        },
        {
          name: "病児保育向け\n保育園検索サービス",
          logo: "childcare.png",
          description: `「お子さんが急に熱を出した時に、預かってくれる保育園の預ける流れまでが煩雑でどうしても預けにくい」というニーズを複数のお母さんから聞いたので、\nデザイナーの知人と組んで個人開発レベルでプロダクトを開発中。サーバーサイドとクライアントサイドの両方を担当。`,
          technologies: [
            {
              name: "VueJS",
              icon: "mdi-vuejs",
              link: ""
            },
            {
              name: "Vuetify",
              icon: "mdi-vuetify",
              link: ""
            },
            {
              name: "Ruby",
              icon: "mdi-language-ruby",
              link: ""
            },
            {
              name: "Rails",
              icon: "mdi-language-ruby-on-rails",
              link: ""
            },
            {
              name: "Docker",
              icon: "mdi-docker",
              link: ""
            },
            {
              name: "AWS",
              icon: "mdi-aws",
              link: ""
            }
          ],
        },
        {
          name: "ポートフォリオサイト",
          logo: "portfolio.png",
          description: `「何をやってきたか？」を可視化かつ記録するためにポートフォリオサイトを作成。\n今後も機能追加や改修予定。\n \n \n \n \n`,
          technologies: [
            {
              name: "VueJS",
              icon: "mdi-vuejs",
              link: ""
            },
            {
              name: "Vuetify",
              icon: "mdi-vuetify",
              link: ""
            },
            {
              name: "Firebase",
              icon: "mdi-firebase",
              link: ""
            },

          ],
        },
      ],
      contactLinks: [
        {
          name: "Email",
          value: "tatsuaki0905.climbing@gmail.com",
          link: "mailto:tatsuaki0905.climbing@gmail.com",
          icon: "mdi-email"
        },
        {
          name: "Github",
          value: "TatsuakiIto",
          link: "https://github.com/TatsuakiIto",
          icon: "mdi-github"
        },
        {
          name: "Facebook",
          value: "Tatsuaki Ito",
          link: "https://www.facebook.com/tatsuaki.itoh",
          icon: "mdi-facebook"
        }
      ]
    };
  }
};
</script>
