<template>
  <div class="main">
    <div class="module-intro">
      <div class="content">
        <div class="left">
          <div class="name">
            至轻云
          </div>
          <div class="slogan">
            轻量级大数据计算平台
          </div>
          <div class="command">
            <p id="command-shell">docker run -p 8080:8080 isxcode/zhiqingyun</p>
            <SvgIcon
              class="copy-icon"
              name="copy"
              @click="handleCommandCopyClick"
            ></SvgIcon>
          </div>
          <div class="btn-div">
            <div class="guide-btn" @click="handleGuideClick">
              <p>快速入门</p>
            </div>
            <div class="quick-btn" @click="handleQuickClick">
              <p>立即体验</p>
              <SvgIcon name="arrow-right" class="link-right-svg"></SvgIcon>
            </div>
            <div class="movie-btn" @click="toggleVideo">
              <p>视频介绍</p>
            </div>
          </div>
        </div>
        <div class="right">
          <div v-show="!isMobile||showVideo" class="artplayer-app"></div>
        </div>
      </div>
    </div>
    <div class="module-about">
      <div class="content">
        <div class="why-title">
          选择至轻云
        </div>
        <div class="why-content">
          至轻云是一款超轻量级、企业级大数据计算平台。一键部署，开箱即用。可快速实现大数据ETL、实时计算、可视化调度、自定义接口、数据大屏、分享表单等场景。助力企业处理海量数据，获得更多商业价值。
        </div>
        <div class="why-content-mobile">
          至轻云是一款超轻量级、企业级大数据计算平台。一键部署，开箱即用。可快速实现大数据ETL、实时计算、可视化调度、自定义接口、数据大屏、分享表单等场景。
        </div>
        <div class="tech-title">
          相关技术
        </div>
        <div class="tech-img-div">
          <img class="tech-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/tech-img/t-k8s.png" alt="">
          <img class="tech-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/tech-img/t-hadoop.png" alt="">
          <img class="tech-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/tech-img/t-spark.png" alt="">
          <img class="tech-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/tech-img/t-hive.png" alt="">
          <img class="tech-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/tech-img/t-doris.png" alt="">
          <img class="tech-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/tech-img/t-clickhouse.png" alt="">
        </div>
      </div>
    </div>
    <div class="module-feat-left">
      <div class="content">
        <div class="left">
          <img id="zoom" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-1.jpg" alt="">
        </div>
        <div class="left-phone">
          <img src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-1.jpg" alt="">
        </div>
        <div class="right">
          <div class="line-1">能写代码？不单单只有Sql</div>
          <div class="line-2">支持超多作业类型，包括SparkSql、SparkJar、数据同步、JdbcSql、Prql、Excel导入、Python脚本、Bash脚本、Curl脚本、接口调用等。</div>
          <div class="line-3" @click="handleQuickClick">立即体验</div>
        </div>
      </div>
    </div>
    <div class="module-feat-right">
      <div class="content">
        <div class="right-phone">
          <img src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-2.jpg" alt="">
        </div>
        <div class="left">
          <div class="line-1">作业调度，横竖都能拖拽</div>
          <div class="line-2">支持全量的作业生命周期指令，包括运行、中止、中断、下线、发布、重跑、重跑下游、重跑当前、外部调用等。</div>
          <div class="line-3" @click="handleQuickClick">立即体验</div>
        </div>
        <div class="right">
          <img id="zoom" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-2.jpg" alt="">
        </div>
      </div>
    </div>
    <div class="module-feat-left">
      <div class="content">
        <div class="left">
          <img id="zoom" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-3.jpg" alt="">
        </div>
        <div class="left-phone">
          <img src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-3.jpg" alt="">
        </div>
        <div class="right">
          <div class="line-1">实时计算，让数据更高效</div>
          <div class="line-2">支持实时计算和数据库实时同步功能，利用Kafka和Debezium高效处理数据流，确保数据的快速传输和更新。</div>
          <div class="line-3" @click="handleQuickClick">立即体验</div>
        </div>
      </div>
    </div>
    <div class="module-business">
      <div class="content">
        <div class="line-1">数据创造价值，大数据创造大价值</div>
        <div class="line-2">AI已至，至轻云与您携手实现企业级大数据平台落地</div>
        <div class="business-img">
          <img src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-1.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-2.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-3.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-4.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-5.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-6.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-7.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-8.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-9.png" alt="">
          <img class="bus-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/business-img/b-10.png" alt="">
        </div>
      </div>
    </div>
    <div class="module-feat-right">
      <div class="content">
        <div class="right-phone">
          <img class="feat-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-4.jpg" alt="">
        </div>
        <div class="left">
          <div class="line-1">多平台部署，从不娇生惯养</div>
          <div class="line-2">支持多种资源调度平台，如Kubernetes、Yarn、CDH、Apache Hadoop、Spark Standalone、Spark Cluster等。</div>
          <div class="line-3" @click="handleQuickClick">立即体验</div>
        </div>
        <div class="right">
          <img id="zoom" class="feat-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-4.jpg" alt="">
        </div>
      </div>
    </div>
    <div class="module-feat-left">
      <div class="content">
        <div class="left">
          <img id="zoom" class="feat-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-5.jpg" alt="">
        </div>
         <div class="left-phone">
          <img class="feat-img" src="https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/p-5.jpg" alt="">
        </div>
        <div class="right">
          <div class="line-1">数据大屏，展示大数据</div>
          <div class="line-2">强大的数据处理和可视化技术，将复杂数据转化为直观图表，支持实时监控和分析，助力企业决策，灵活适应行业内需求。</div>
          <div class="line-3" @click="handleQuickClick">立即体验</div>
        </div>
      </div>
    </div>
    <div class="module-end">
      <div class="content">
        <div class="line-1">开源助力企业运用大数据能力</div>
        <div class="end-btn" @click="handleQuickClick">免费试用</div>
      </div>
    </div>
  </div>
  <LayoutHomeFooter/>
</template>

<script lang="ts" setup>
import {ElMessage} from 'element-plus'
import Artplayer from "artplayer";
import {defineProps} from "vue";
import mediumZoom from "medium-zoom";

onMounted(async () => {
    await nextTick()
    mediumZoom(document.querySelectorAll('#zoom'),{
       margin: 100,
       scrollOffset: 1,
       background: '#fffaf8',
    })
})

definePageMeta({
  title: "首页",
  layout: "home",
});

useSeoMeta({
  title: "至轻云",
  ogTitle: "至爻数据",
  description: "企业级大数据计算平台",
  ogDescription: "打造企业级开源软件全家桶",
});

const isMobile = useMediaQuery('(max-width: 767px)')

const props = defineProps({
  showVideo: {
    type: Boolean,
    default: false,
  },
})

const showVideo = ref(props.showVideo)

const toggleVideo = () => {
  showVideo.value = !showVideo.value
}

onMounted(() => {
  const art = new Artplayer({
    container: '.artplayer-app',
    url: 'https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/product.mp4',
    poster:'https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/product-img/product.jpg',
    fullscreen: true,
    fullscreenWeb: true,
    pip: true,
    autoplay: false,
    theme: '#e25a1b',
    muted: false,
    autoSize: true
  });
  window.addEventListener("scroll", handleScroll);
})

function handleScroll() {
  if (window.scrollY > 50) {
    showVideo.value = false;
  }
}

function handleGuideClick() {
  const router = useRouter();
  router.push("/docs/zh/0/0");
}

function handleQuickClick() {
  window.open("https://zhiqingyun-demo.isxcode.com");
}

function handleCommandCopyClick() {
  const codeBlock = document.getElementById("command-shell");
  const codeBlockText = codeBlock?.innerText;
  if (codeBlockText) {
    copyContent(codeBlockText);
  }
}

const copyContent = async (text: string) => {
  try {
    await navigator.clipboard.writeText(text);
    ElMessage({
      duration: 800,
      message: '复制成功',
      type: 'success',
    });
  } catch (err) {
    console.error("Failed to copy: ", err);
  }
};

</script>

<style lang="scss" scoped>

@font-face {
  font-family: "阿里妈妈数黑体 Bold";font-weight: 700;src: url("//at.alicdn.com/wf/webfont/UMV2yX61q8rB/OobtoafRisR7.woff2") format("woff2"),
  url("//at.alicdn.com/wf/webfont/UMV2yX61q8rB/YMgEswp0IFDQ.woff") format("woff");
  font-display: swap;
}

@font-face {
  font-family: "阿里巴巴普惠体 2.0 45 Light";font-weight: 300;src: url("//at.alicdn.com/wf/webfont/UMV2yX61q8rB/ZluNSZ10rnKR.woff2") format("woff2"),
  url("//at.alicdn.com/wf/webfont/UMV2yX61q8rB/ADm74pBC0zsx.woff") format("woff");
  font-display: swap;
}

$font-size: 14px;
// 介绍的高度
$module-intro-height: 850px;
// 相关技术板块的高度
$module-about-height: 460px;
// 商业板块的高度
$module-business-height: 550px;
// 主题色
$primary-color: #e25a1b;
// 特点1背景色
$module-feat-left-bg-color: white;
// 特点2背景色
$module-feat-right-bg-color: rgba(255, 156, 110, 5%);
// 特点高度
$module-feat-height: 440px;
// 结束板块高度
$module-end-height: 300px;
// 结束板块高度
$primary-width: 1200px;
// 产品介绍图片大小
$module-intro-img-width: 600px;


.main {

  font-family: "阿里巴巴普惠体 2.0 45 Light", sans-serif;

  .module-intro {
    width: 100%;
    height: $module-intro-height;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    background-image: url('https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/web-img/bg-0.jpg');
    padding-top: 200px;
    position: relative;
    overflow: hidden;

    .bg-video {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 105%;
      object-fit: cover;
      z-index: -1;
      pointer-events: none;
    }

    .content {
      display: flex;

      .left {
        width: 600px;;

        .name {
          margin-top: 120px;
          font-family: "阿里妈妈数黑体 Bold", sans-serif;
          font-size: 60px;
        }

        .slogan {
          margin-top: 20px;
          font-family: "阿里妈妈数黑体 Bold", sans-serif;
          font-size: 40px;
        }

        .command {
          display: flex;
          margin-top: 20px;
          padding-left: 15px;
          border: #e25a1b solid 1px;
          color: #e25a1b;
          width: 435px;
          border-radius: 3px;
          font-size: 17px;
          height: 38px;
          line-height: 38px;

          .copy-icon {
            cursor: pointer;
            margin-left: 15px;
            margin-top: 6px;
            width: 24px;
            height: 24px;
          }
        }

        .btn-div {
          margin-top: 25px;
          display: flex;

          .guide-btn {
            cursor: pointer;
            width: 120px;
            border-radius: 3px;
            background: #e25a1b;
            color: white;
            text-align: center;
            font-size: 18px;
            height: 40px;
            line-height: 40px;
          }

          .movie-btn {
            display: none;
          }

          .quick-btn {
            cursor: pointer;
            margin-left: 20px;
            width: 150px;
            color: #e25a1b;
            height: 40px;
            line-height: 40px;
            text-align: center;
            display: flex;

            .link-right-svg {
              margin-top: 10px;
              width: 20px;
              height: 20px;
            }
          }
        }
      }

      .right {
        .artplayer-app {
          height: 341px;
          margin-top: 70px;
          width: 630px;
        }
      }
    }
  }

  .module-about {
    width: 100%;
    background: white;
    height: $module-about-height;
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 40px;

    .content {
      .why-title {
        margin: auto;
        text-align: center;
        width: 400px;
        font-family: "阿里妈妈数黑体 Bold", sans-serif;
        font-size: 30px;
      }

      .why-content {
        margin: 25px auto auto;
        text-indent: 2em;
        width: 850px;
        line-height: 26px;
        font-size: 18px;
      }

      .why-content-mobile {
        display: none;
      }

      .tech-title {
        text-align: center;
        margin: 40px auto auto;
        width: 400px;
        font-size: 12px;
        color: lightgray;
      }

      .tech-img-div {

        .tech-img {
          cursor: pointer;
        }

        display: flex;
        justify-content: space-between;
        margin: 20px auto auto;
        width: 1200px;

        img {
          width: 150px;
          height: 55px;
        }
      }
    }
  }

  .module-business {
    width: 100%;
    height: $module-business-height;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    background-image: url('https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/web-img/bg-2.jpg');
    display: flex;
    align-items: center;
    justify-content: center;

    .content {
      .line-1 {
        margin-top: 50px;
        color: white;
        text-align: center;
        font-family: "阿里妈妈数黑体 Bold", sans-serif;
        font-size: 35px;
      }

      .line-2 {
        margin-top: 16px;
        color: white;
        text-align: center;
      }

      .business-img {
        margin: 40px auto auto;
        width: 1200px;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;

        img {
          width: 220px;
          height: 150px;
          margin: 6px;
        }
      }
    }
  }
}

.module-feat-left {
  width: 100%;
  height: $module-feat-height;
  background: $module-feat-right-bg-color;
  display: flex;
  align-items: center;
  justify-content: center;

  .content {
    display: flex;

    .left-phone {
      display: none;
    }

    .left {
      width: 600px;;

      img {
        width: 450px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
      }
    }

    .right {
      margin-left: 100px;
      margin-top: 50px;
      width: 600px;;

      .line-1 {
        font-family: "阿里妈妈数黑体 Bold", sans-serif;
        font-size: 30px;
      }

      .line-2 {
        width: 560px;
        height: 55px;
        font-size: 17px;
        margin-top: 30px;
        line-height: 24px;
      }

      .line-3 {
        cursor: pointer;
        margin-top: 35px;
        color: #e25a1b;
        font-family: "阿里妈妈数黑体 Bold", sans-serif;
      }
    }
  }

}

.module-feat-right {
  width: 100%;
  height: $module-feat-height;
  display: flex;
  align-items: center;
  justify-content: center;
  background: $module-feat-left-bg-color;

  .content {
    display: flex;

    .right-phone {
      display: none;
    }

    .right {
      width: 600px;
      margin-left: 100px;

      img {
        width: 450px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
      }
    }

    .left {
      width: 600px;;
      margin-top: 50px;

      .line-1 {
        font-family: "阿里妈妈数黑体 Bold", sans-serif;
        font-size: 30px;
      }

      .line-2 {
        width: 560px;
        height: 55px;
        font-size: 17px;
        margin-top: 30px;
        line-height: 24px;
      }

      .line-3 {
        cursor: pointer;
        margin-top: 35px;
        color: #e25a1b;
        font-family: "阿里妈妈数黑体 Bold", sans-serif;
      }
    }
  }
}

.module-end {
  height: $module-end-height;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-image: url('https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/web-img/bg-1.jpg');
  display: flex;
  align-items: center;
  justify-content: center;

  .content {
    .line-1 {
      width: 600px;
      text-align: center;
      color: white;
      margin: auto;
      font-family: "阿里妈妈数黑体 Bold", sans-serif;
      font-size: 40px;
    }

    .end-btn {
      cursor: pointer;
      margin: 40px auto auto;
      background: white;
      color: #e25a1b;
      width: 200px;
      font-size: 20px;
      border-radius: 3px;
      height: 40px;
      line-height: 40px;
      text-align: center;
    }
  }
}

.content {
  margin: auto;
  width: $primary-width;
}

// ------------------------------------------------------- 移动端 ----------------------------------------------------------------------

@media (max-width: 768px) {

  .main {

    .module-intro {
      width: 100%;
      height: 850px;
      padding-top: 400px;

      .content {
        display: flex;

        .right {
          position: fixed;
          top: 30%;
          left: 50%;
          transform: translate(-50%, -50%);

          .artplayer-app {
            height: 195px;
            margin-top: 70px;
            width: 360px;
          }
        }

        .left {
          width: 400px;

          .name {
            text-align: center;
            margin-top: 10px;
            font-family: "阿里妈妈数黑体 Bold", sans-serif;
            font-size: 66px;
          }

          .slogan {
            margin-top: 20px;
            text-align: center;
            font-family: "阿里妈妈数黑体 Bold", sans-serif;
            font-size: 27px;
          }

          .command {
            display: none;
          }

          .btn-div {
            display: flex;
            width: 300px;
            margin: 25px auto auto;

            .guide-btn {
              display: none;
              cursor: pointer;
              width: 170px;
              border-radius: 3px;
              background: #e25a1b;
              color: white;
              text-align: center;
              font-size: 18px;
              height: 40px;
              line-height: 40px;
              margin-left: 40px;
            }

            .quick-btn {
              display: none;
            }

            .movie-btn {
              cursor: pointer;
              width: 150px;
              margin: auto;
              background: #e25a1b;
              color: white;
              height: 40px;
              line-height: 40px;
              text-align: center;
              font-size: 20px;
              display: block;
              border-radius: 3px;
            }
          }
        }
      }
    }

    .module-about {
      width: 100%;
      background: white;
      height: 350px;
      display: flex;
      align-items: center;
      justify-content: center;
      padding-top: 40px;

      .content {
        .why-title {
          margin: auto;
          text-align: center;
          width: 300px;
          font-family: "阿里妈妈数黑体 Bold", sans-serif;
          font-size: 30px;
        }

        .why-content-mobile {
          display: block;
          margin: 25px auto auto;
          width: 300px;
          line-height: 25px;
          font-size: 19px;
          text-indent: 2em;
        }

        .why-content {
          display: none;
        }

        .tech-title {
          display: none;
        }

        .tech-img-div {
          display: none;
        }
      }
    }

    .module-business {
      width: 100%;
      height: 320px;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      background-image: url('https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/web-img/bg-2.jpg');
      align-items: center;

      .content {
        height: 350px;

        .line-1 {
          color: white;
          text-align: center;
          font-family: "阿里妈妈数黑体 Bold", sans-serif;
          font-size: 20px;
        }

        .line-2 {
          margin-top: 16px;
          color: white;
          text-align: center;
          font-size: 13px;
        }

        .business-img {
          margin: 20px auto auto;
          width: 300px;

          .bus-img {
            display: none;
          }

          img {
            width: 250px;
          }
        }
      }
    }
  }

  .module-feat-left {
    width: 100%;
    height: 480px;
    display: flex;
    align-items: center;
    justify-content: center;

    .content {
      height: 380px;
      flex-direction: column;

      .left {
        display: none;
      }

      .left-phone{
        display: block;
        width: 300px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);

        img {
          width: 300px;
        }
      }

      .right {
        margin-left: 0;
        margin-top: 20px;
        width: 300px;

        .line-1 {
          margin-top: 15px;
          font-family: "阿里妈妈数黑体 Bold", sans-serif;
          font-size: 25px;
          text-align: center;
        }

        .line-2 {
          height: 100px;
          width: 300px;
          margin-top: 30px;
          line-height: 25px;
          font-size: 18px;
        }

        .line-3 {
          display: none;
        }
      }
    }

  }

  .module-feat-right {

    width: 100%;
    height: 480px;
    display: flex;
    align-items: center;
    justify-content: center;

    .content {
      height: 380px;
      flex-direction: column;

      .right {
        display: none;
      }

      .right-phone {
        display: block;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);

        img {
          width: 300px;
        }
      }

      .left {
        margin-left: 0;
        margin-top: 20px;
        width: 300px;

        .line-1 {
          margin-top: 15px;
          font-family: "阿里妈妈数黑体 Bold", sans-serif;
          font-size: 25px;
          text-align: center;
        }

        .line-2 {
          height: 100px;
          width: 300px;
          margin-top: 30px;
          line-height: 25px;
          font-size: 18px;
        }

        .line-3 {
          display: none;
        }
      }
    }
  }

  .module-end {
    height: 300px;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    background-image: url('https://isxcode.oss-cn-shanghai.aliyuncs.com/zhiqingyun/web-img/bg-1.jpg');
    display: flex;
    align-items: center;
    justify-content: center;

    .content {
      .line-1 {
        width: 300px;
        text-align: center;
        color: white;
        margin: auto;
        font-family: "阿里妈妈数黑体 Bold", sans-serif;
        font-size: 40px;
      }

      .end-btn {
        display: none;
      }
    }
  }

  .content {
    margin: auto;
    width: 300px;
  }

}
</style>
