<template>
  <section class="msite">
    <div class="miste-content-wrapper">
      <div class="miste-content">
        <!--首页导航-->
        <HeaderTop title="123424343434354454654645664646546">
          <span class="header_search" solt="left">
            <i class="iconfont icon-sousuo"></i>
          </span>
          <span class="header_login" solt="right">
            <i class="header_login_text">登录|注册</i>
          </span>
        </HeaderTop>
        <nav class="msite_nav">
          <div class="swiper-container">
            <div class="swiper-wrapper">
              <div class="swiper-slide">
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/1.jpg" />
                  </div>
                  <span>{{ 13213 }}</span>
                </a>
              </div>
            </div>
            <!-- Add Pagination -->
            <div class="swiper-pagination"></div>
          </div>
          <img src="./images/msite_back.svg" alt="back" />
        </nav>
        <!--首页附近商家-->
        <div class="msite_shop_list">
          <div class="shop_header">
            <i class="iconfont icon-xuanxiang"></i>
            <span class="shop_header_title">附近商家</span>
          </div>
          <ShopList />
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import HeaderTop from "../../components/HeaderTop/HeaderTop";
import ShopList from "../../components/ShopList/ShopList";
import Swiper from "swiper";
import "swiper/swiper.min.css";
export default {
  mounted() {
    //创建swiper对象，实现轮播
    new Swiper(".swiper-container", {
      loop: true,
      pagination: {
        el: ".swiper-pagination",
      },
    });
  },
  components: {
    HeaderTop,
    ShopList,
  },
};
</script>
<style lang="stylus" rel="stylesheet/stylus">
@import '../../common/stylus/mixins.styl';

.msite { // 首页
  width: 100%;

  .miste-content-wrapper {
    position: fixed;
    top: 45px;
    bottom: 46px;
    width: 100%;

    .msite_nav {
      bottom-border-1px(#e4e4e4);
      margin-top: 15px;
      height: 200px;
      background: #fff;

      .swiper-container {
        width: 100%;
        height: 100%;

        .swiper-wrapper {
          width: 100%;
          height: 100%;

          .swiper-slide {
            display: flex;
            justify-content: center;
            align-items: flex-start;
            flex-wrap: wrap;

            .link_to_food {
              width: 25%;

              .food_container {
                display: block;
                width: 100%;
                text-align: center;
                padding-bottom: 10px;
                font-size: 0;

                img {
                  display: inline-block;
                  width: 50px;
                  height: 50px;
                }
              }

              span {
                display: block;
                width: 100%;
                text-align: center;
                font-size: 13px;
                color: #666;
              }
            }
          }
        }

        .swiper-pagination {
          >span.swiper-pagination-bullet-active {
            background: #02a774;
          }
        }
      }
    }

    .msite_shop_list {
      top-border-1px(#e4e4e4);
      margin-top: 10px;
      background: #fff;

      .shop_header {
        padding: 10px 10px 0;

        .shop_icon {
          margin-left: 5px;
          color: #999;
        }

        .shop_header_title {
          color: #999;
          font-size: 14px;
          line-height: 20px;
        }
      }
    }
  }
}
</style>