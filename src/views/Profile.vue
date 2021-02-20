<template>
  <div class="wrapper">
    <parallax
      class="section page-header header-filter"
      :style="headerStyle"
    ></parallax>
    <div class="main main-raised">
      <div class="section profile-content">
        <div class="container">
          <div class="md-layout">
            <div class="md-layout-item md-size-50 mx-auto">
              <div class="profile">
                <div class="avatar">
                  <img
                    :src="img"
                    alt="Circle Image"
                    class="img-raised rounded-circle img-fluid"
                  />
                </div>
                <div class="name">
                  <h2 class="title">房建樺</h2>
                  <h6>Jasper</h6>
                  <!-- <md-button
                    href="javascript:void(0)"
                    class="md-just-icon md-simple md-dribbble"
                    ><i class="fab fa-dribbble"></i
                  ></md-button>
                  <md-button
                    href="javascript:void(0)"
                    class="md-just-icon md-simple md-twitter"
                    ><i class="fab fa-twitter"></i
                  ></md-button>
                  <md-button
                    href="javascript:void(0)"
                    class="md-just-icon md-simple md-pinterest"
                    ><i class="fab fa-pinterest"></i
                  ></md-button> -->
                </div>
              </div>
            </div>
          </div>
          <div class="description text-center">
            <p>
              我熱愛多變的生活，持續的挑戰並不斷迎接新事物，為每個日子注入了動力。樂於接受挑戰並持續成長。熱衷於慢跑、旅行、攝影，體驗生活的芬芳以及與同好互動的樂趣。
            </p>
          </div>
          <div class="profile-tabs">
            <tabs
              :tab-name="['Education', 'Work Experience', 'Project','others']"
              :tab-icon="['face', 'list', 'dashboard','camera']"
              plain
              nav-pills-icons
              color-button="success"
            >
              <!-- here you can add your content for tab-content -->
              <template slot="tab-pane-1">
                <div class="md-layout">
                <div class="md-layout-item">
                  <h2><strong>國立成功大學 交通管理研究所</strong></h2>
                  <h3>2013/09 - 2015/07</h3>
                  <h4>就讀研究所期間，著重於求解最佳化問題，並修習網路分析、最佳化演算法、程式設計(C/C#...)<br>
                      研究項目為建立台鐵旅客考量車輛擁擠度、乘車票價後的搭乘路徑選擇模型，並透過啟發式演算法求得系統最佳解。 <br>
                      後續成果刊載於國際期刊(<a href="https://www.tandfonline.com/doi/abs/10.1080/19427867.2017.1343764?journalCode=ytrl20">Transportation Letters , Jun 2017</a>   )
                  </h4>                    
                </div>
                </div>
              </template>
              <template slot="tab-pane-2">
                <div class="md-layout">
                <div class="md-layout-item">
                  <h2><strong>台灣國際航電 (GARMIN) 製程測試工程師</strong></h2>
                  <h3>2016/10 - </h3>
                  <h4>主要負責產線測試資料分析、系統/工具開發、測試優化、產品測試導入，參與公司 I4.0 MES系統導入、測試分析網頁開發、AOEM專案。<br>
                      得以深入的了解電子製造業各製程段的需求及問題，並更精準地解決問題。
                  </h4>                    
                </div>
                </div>
              </template>
              <template slot="tab-pane-3">
                <div class="md-layout">
                  <div class="md-layout-item">
                  <h2><strong>PTE Web測試良率儀表</strong></h2>
                  <h3>2018/06 - 2020/05</h3>
                  <h4>負責範疇：</h4>
                    <ul>
                      <li>前端功能開發(ASP.NET MVC 5/ VueJS)</li>
                      <li>後端資料處理 (APIs)</li>
                      <li>排程工具(C#/Python)</li>
                    </ul>
                  <h4>實現功能：</h4>
                    <ul>
                      <li>廠域產線測試表現儀表</li>
                      <li>產線測試良率分析 / 產線測試效率分析 / 即時產出效率分析</li>
                      <li>自動異常歸類</li>
                      <li>Issue Alert / Issue track</li>
                    </ul>
                  <h4>具體效益：</h4>
                    <ul>
                      <li>提升工程人員處理效率</li>
                      <li>統整分析工具，簡便維護</li>
                      <li>主動追蹤異常</li>
                    </ul>   
                </div>
                <div class="md-layout-item">
                  <h2><strong></strong></h2>  <br/>
                  <md-card>
                    <carousel
                      :per-page="1"
                      loop
                      :speed="700"
                      autoplay
                      :autoplay-timeout="5000"
                      :mouse-drag="false"
                      navigationEnabled
                      navigationNextLabel="<i class='material-icons'>keyboard_arrow_right</i>"
                      navigationPrevLabel="<i class='material-icons'>keyboard_arrow_left</i>"
                    >
                      <slide>
                        <img :src="carousel1" alt="carousel1" />
                      </slide>
                      <slide>
                        <img :src="carousel2" alt="carousel2" />
                      </slide>
                      <slide>
                        <img :src="carousel3" alt="carousel3" />
                      </slide>
                      <slide>
                        <img :src="carousel4" alt="carousel4" />
                      </slide>              
                    </carousel>
                  </md-card>                
                </div>                
                </div>
                <div class="md-layout">
                  <div class="md-layout-item">
                  <h2><strong>AOI 複判系統</strong></h2>
                  <h3>2017/06 - 2019/06</h3>
                  <h4>負責範疇：</h4>
                    <ul>
                      <li>AOI 後復判資料處理系統 (WPF)</li>
                    </ul>
                  <h4>實現功能：</h4>
                    <ul>
                      <li>異常點位警示</li>
                      <li>復判資料流處理</li>
                      <li>AOI輸出之圖像處理</li>
                    </ul>
                  <h4>具體效益：</h4>
                    <ul>
                      <li>搭配自動分板機使用，每線節省50%人力</li>
                      <li>最高應用於全廠2/3產線</li>                      
                    </ul>   
                </div>
                <div class="md-layout-item">
                  <h2><strong></strong></h2> <br/>    
                  <md-card>
                    <carousel
                      :per-page="1"
                      loop
                      :speed="700"
                      autoplay
                      :autoplay-timeout="5000"
                      :mouse-drag="false"
                      navigationEnabled
                      navigationNextLabel="<i class='material-icons'>keyboard_arrow_right</i>"
                      navigationPrevLabel="<i class='material-icons'>keyboard_arrow_left</i>"
                    >
                      <slide>
                        <img :src="carousel5" alt="carousel5" />
                      </slide>           
                    </carousel>
                  </md-card>                                     
                </div>
                </div>
              </template>
              <template slot="tab-pane-4">
                <div class="md-layout">
                <!-- <div class="col-md-3">
                  <h2><strong>國立成功大學 交通管理研究所</strong></h2>
                  <h3>2013/09 - 2015/07</h3>
                  <h4>就讀研究所期間，著重於求解最佳化問題，並學習網路分析、最佳化演算法、程式設計…等技能。<br>
                      後續研究成果刊載於國際期刊(<a href="https://www.tandfonline.com/doi/abs/10.1080/19427867.2017.1343764?journalCode=ytrl20">Transportation Letters , Jun 2017</a>   )
                  </h4>                    
                </div> -->
                </div>
              </template>
            </tabs>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Tabs } from "@/components";
export default {
  components: {
    Tabs
  },
  bodyClass: "profile-page",
  data() {
    return {
      carousel1: require("@/assets/img/PTEWeb_1.png"),
      carousel2: require("@/assets/img/PTEWeb_2.png"),
      carousel3: require("@/assets/img/PTEWeb_3.png"),
      carousel4: require("@/assets/img/PTEWeb_4.png"),
      carousel5: require("@/assets/img/AOI_1.png")
      // tabPane1: [
      //   { image: require("@/assets/img/examples/studio-1.jpg") },
      //   { image: require("@/assets/img/examples/studio-2.jpg") },
      //   { image: require("@/assets/img/examples/studio-4.jpg") },
      //   { image: require("@/assets/img/examples/studio-5.jpg") }
      // ],
      // tabPane2: [
      //   { image: require("@/assets/img/examples/olu-eletu.jpg") },
      //   { image: require("@/assets/img/examples/clem-onojeghuo.jpg") },
      //   { image: require("@/assets/img/examples/cynthia-del-rio.jpg") },
      //   { image: require("@/assets/img/examples/mariya-georgieva.jpg") },
      //   { image: require("@/assets/img/examples/clem-onojegaw.jpg") }
      // ],
      // tabPane3: [
      //   { image: require("@/assets/img/examples/mariya-georgieva.jpg") },
      //   { image: require("@/assets/img/examples/studio-3.jpg") },
      //   { image: require("@/assets/img/examples/clem-onojeghuo.jpg") },
      //   { image: require("@/assets/img/examples/olu-eletu.jpg") },
      //   { image: require("@/assets/img/examples/studio-1.jpg") }
      // ]
    };
  },
  props: {
    header: {
      type: String,
      default: require("@/assets/img/view_3.jpg")
    },
    img: {
      type: String,
      default: require("@/assets/img/faces/face_3.jpg")
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.header})`
      };
    }
  }
};
</script>

<style lang="scss" scoped>
.section {
  padding: 0;
}

.profile-tabs::v-deep {
  .md-card-tabs .md-list {
    justify-content: center;
  }

  [class*="tab-pane-"] {
    margin-top: 3.213rem;
    padding-bottom: 50px;

    img {
      margin-bottom: 2.142rem;
    }
  }
}
</style>
