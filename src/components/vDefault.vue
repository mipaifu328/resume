<!--  -->
<template>
  <div class="default">
    <h1 class="main-title">首页</h1>
    <div class="default-container">
      <div class="head-pic"></div>
      <div class="motto">追求：无一日之懈怠，无一事之马虎</div>
      <div class="des-list">
        <p>我叫Mipaifu328</p>
        <P>一名前端开发工程师</P>
        <p>594757223@qq.com</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}

</script>
<style lang="scss" scoped>
  .default{
    position: absolute;
    top: 200px;
    left: 0;
    right: 0;
    bottom: 0;
    .main-title{
      display: none;
    }
    .default-container{
      display: flex;
      flex-direction: column;
      .head-pic{
        display: block;
        margin: 0 auto;
        width: 150px;
        height: 150px;
        border-radius: 50%;
        background: url(../assets/images/mipaifu328.jpg) center center no-repeat;
        /* background: url(http://www.mipaifu328.com/img/mipaifu328.jpg) center center no-repeat; */
        background-size: cover;
        transition: box-shadow .5s linear;
      }
      .motto{
        position: relative;
        padding: 20px 0;
        text-align: center;
        width: 90%;
        max-width: 90%;
        margin: 0 auto;
        color: #FFF;
        font-size: 22px;
        &::after{
          content: "";
          position: absolute;
          left: 10%;
          right: 10%;
          bottom: 0;
          height: 1px;
          background-color: rgba(255,255,255,.6);
        }
      }
      .des-list{
        padding-top: 20px;
        line-height: 20px;
        font-size: 18px;
        p{
          margin: 24px 0;
          text-align: center;
          color: #FFF;
        }
      }
    }
  }
  @media screen and (max-width: 768px){
    .default{
      top:100px;
      .default-container{
        .motto{
          font-size: 18px;
        }
        .des-list{
          font-size: 14px;
        }
      }
    }
  }
  @media screen and (min-width: 1500px){
    .default{
      top:250px;
      .default-container{
        .head-pic{
          width: 200px;
          height: 200px;
        }
        .motto{
          padding: 30px 0;
          font-size: 22px;
        }
        .des-list p{
          margin: 30px 0;
          font-size: 20px;
        }
      }
    }
  }
</style>
