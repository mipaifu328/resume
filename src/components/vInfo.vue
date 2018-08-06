<!--  -->
<template>
  <div class="info">
    <h1 class="main-title">关于我</h1>
    <div class="info-container">
      <ul class="info-list">
        <li>
          <div class="info-img">
            <img src="../assets/images/i_age.svg" alt="age">
          </div>
          <div class="info-txt">年龄/26岁</div>
        </li>
        <li>
          <div class="info-img">
            <img src="../assets/images/i_edu.svg" alt="edu">
          </div>
          <div class="info-txt">学历/本科</div>
        </li>
        <li>
          <div class="info-img">
            <img src="../assets/images/i_site.svg" alt="site">
          </div>
          <div class="info-txt">坐标/广州</div>
        </li>
        <li>
          <div class="info-img">
            <img src="../assets/images/i_status.svg" alt="status">
          </div>
          <div class="info-txt">状态/离职</div>
        </li>
      </ul>
      <div class="info-description">
        <p>三年前端开发经验</p>
        <p>熟悉MVVM开发,深谙自动化,模块化开发之道</p>
        <p>高效的自学能力,具备独立分析解决问题能力</p>
        <p>强烈的自我驱动力,代码强迫症患者</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>
<style lang="scss" scoped>
  .info-container{
    position: absolute;
    top: 200px;
    left: 0;
    right: 0;
    bottom: 0;
    .info-list{
      max-width: 800px;
      margin: 0 auto;
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
      font-size: 18px;
      li{
        width: 100px;
        margin: 0 20px;
        .info-img{
          width: 90px;
          height: 90px;
          cursor: pointer;
          transition: background .2s,-webkit-transform ease-out .1s;
          transition: transform ease-out .1s,background .2s;
          transition: transform ease-out .1s,background .2s,-webkit-transform ease-out .1s;
          background: rgba(255,255,255,.1);
          border-radius: 50%;
          position: relative;
          margin: 0 auto;
          &:hover{
            background: rgba(255,255,255,0.05);
            transform: scale(0.93);
            color: #fff;
          }
          &::after{
            content: '';
            position: absolute;
            box-shadow: 0 0 0 2px rgba(255,255,255,.1);
            opacity: 0;
            transform: scale(.9);
            width: 100%;
            height: 100%;
            border-radius: 50%;
          }
          &:hover:after{
            animation: effect 1.3s ease-out 75ms;
          }
          img{
            width: 50%;
            position: absolute;
            top: 50%;
            right: 50%;
            transform: translateY(-50%) translateX(50%);
          }
        }
        .info-txt{
          text-align: center;
          margin-top: 20px;
          color: #FFF;
        }
      }
    }
    .info-description{
      text-align: center;
      line-height: 24px;
      padding-top: 50px;
      font-size: 18px;
      color: #FFF;
    }
  }
  @keyframes effect {
    0% {
      opacity: 0.3;
    }
    40% {
      opacity: 0.5;
      box-shadow: 0 0 0 2px rgba(255,255,255,0.1), 0 0 10px 10px #109085, 0 0 0 10px rgba(255,255,255,0.5);
    }
    100% {
      box-shadow: 0 0 0 2px rgba(255,255,255,0.1), 0 0 10px 10px #109085, 0 0 0 10px rgba(255,255,255,0.5);
      transform: scale(1.5);
      opacity: 0;
    }
  }
  @media screen and (max-width: 768px){
    .info-container{
      top:100px;
      .info-list{
        li{
          .info-img{
            width: 50px;
            height: 50px;
          }
          .info-txt{
            font-size: 12px;
            margin: 20px 0;
          }
        }
        .info-description{
          font-size: 14px;
        }
      }
    }
  }
  @media screen and (min-width: 1500px){
    .info-container{
      top: 300px;
      left: 0;
      right: 0;
      bottom: 0;
      .info-list{
        max-width: 1200px;
        li{
          width: 150px;
          margin: 0 20px;
          .info-img{
            width: 120px;
            height: 120px;
          }
        }
      }
      .info-description{
        text-align: center;
        line-height: 30px;
        padding-top: 100px;
        font-size: 20px;
        color: #FFF;
      }
    }
  }
</style>
