<template>
  <div class="home">
    <div class="topnav">
      <div class="inner">
      <img alt="BOM Logo" src="../assets/img/BOM_logo_rgba@3x.png" />
      <span class="title">{{translate("title1")}}
        <span class="textBlue">{{translate("title2")}}
          </span> {{translate("title3")}}
            <span class="textBlue">{{translate("title4")}} 
              </span>{{translate("title5")}}</span>

      <select class="switcher" name="lang" v-model="lang">
      <option value="nl">NL</option>
      <option value="en">EN</option>
      </select>
      
      </div>
    </div>
  <div class="afterNav">
    <video class="video" id="video" preload="metadata" playsinline controls>
        <source id='source' data-video src='../assets/videos/video_engels.mp4' type='video/mp4'/>
    </video>
    
    <div>
        <div class="share">
            <span>{{translate("share")}}</span>
            <a class="button-social"  @click="triggerWhatsapp"><img alt="Whatsapp Button" src="../assets/img/icon_whatsapp@1x.png"/></a>
            <a class="button-social" @click="triggerFacebook"><img alt="Facebook Button" src="../assets/img/icon_facebook@1x.png"/></a>
            <a class="button-social" href="../assets/videos/video_engels.mp4"  download="video.mp4"><img alt="Download Button" src="../assets/img/icon_arrow@1x.png"/></a>
        </div>
        
        <div class="description">
            <h1>BOM Catalyzing Change.</h1>
            <div class="text">{{translate("description")}}</div>
            <a class="button-description" href="https://www.bom.nl/over-bom" target="_blank">{{translate("button1")}}</a>
            <a class="button-description" href="https://www.bom.nl/inschrijven-nieuwsbrief" target="_blank">{{translate("button2")}}</a>
        </div>
    </div>
    </div>
  </div>
</template>


<script>
import en from '@/assets/data/en.js'
import nl from '@/assets/data/nl.js'

export default {
  mixins: [en, nl],
  name: "Home",
  components: {
  },
  data(){
    return{
      lang: "nl",
    };
  },
  methods: {
    translate(prop){
      return this[this.lang][prop];
    },
     triggerFacebook() {
      const url = `https://www.facebook.com/sharer/sharer.php?u=test`;
      window.open(
        url,
        "facebook",
        "width=550,height=450,scrollbars=yes,toolbar=no,location=yes"
      );
    },
    triggerWhatsapp() {
      const url = `https://wa.me/?text=222222`;
      window.open(url);
    },
  },
};
</script>

<style lang="scss" scoped>

.home{
  width: 100%;
  min-width: 464px;

.topnav{
  overflow: hidden;
  min-width: 100%;
  height: 88px;
  background-color: rgb(255, 255, 255);
    @include tablet-down{
      height: 144px;
    }
  .inner{
    padding-top: 16px;
    width: 85%;
    display: table;
    margin: 0 auto;
    img {
      margin-bottom: 28px;
      width: 150px;
      height: 56px; 
      float: left;
      @include tablet-down{
        width: 86px;
        height: 32px; 
        margin-left: auto;
        margin-right: auto;
        float: none;
        display: block;
      }
    }
  .title {
    font-size: 24px;
    line-height: 32px;
    color: #DD1122;
    font-family: ScalaSans;
    line-height: 32px;
    .textBlue{
      color: #112266;
    }
    @include tablet-down{
      font-size: 20px;
      line-height: 26px;
    }
  }
  .switcher{
	  appearance: none;
    padding: 5px;
    background-color: #112266;
    color: white;
    border-radius: 5px;
    border: none;
    float: right;
    @include tablet-down{
      font-size: 20px;
      line-height: 26px;
      position: absolute;
      top: 19px;
      right: 16px;
    }
    @include desktopxl-down{
      font-size: 20px;
      line-height: 26px;
      position: absolute;
      top: 19px;
      right: 16px;
    }
  }
  
  }
}

.afterNav{
  background-image:url("../assets/img/banner_desktop@3x.png");
  background-size: 100%;
  background-repeat: no-repeat;
.share{
  width: 100%;
  padding-top: 24px;
  span {
      color: #FFFFFF;
      font-family: DINPro;
      font-size: 16px;
      line-height: 24px;
      text-align: center;
      padding-right: 14px;
      @include tablet-down{
        display: block;
        margin-bottom: 28px;
      }
  }
  .button-social {
      cursor: pointer;
      border-radius: 50%;
      background-color: #ffffff;
      border: none;
      padding: 16px;
      text-decoration: none;
      margin-right: 8px;
      margin-left: 8px;
      img{
        width: 16px;
        height: 16px;
        }
  }
}

.video {
    margin-top: 56px;
    width: 60%;
    height: auto;
    @include tablet-down{
        width: 90%;
    }
}

.description{
  width: 100%;
    h1 {
        margin-top: 32px;
        color: #FFFFFF;
        font-family: DINPro;
        font-size: 28px;
        line-height: 32px;
        text-align: center;
    }
    .text{
        max-width: 60%;
        min-width: 60%;
        margin: auto;
        color: #FFFFFF;
        font-family: DINPro;
        font-size: 16px;
        line-height: 24px;
        width: 792px;
        text-align: left;
        padding-bottom: 24px;
        @include tablet-down{
          max-width: 90%;
        }
    }
    .button-description{
        margin-left: 12px;
        margin-right: 12px;
        background-color: #112266;
        border: none;
        color: rgb(255, 255, 255);
        padding: 11px 33px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        cursor: pointer;
        border-radius: 33px;
        border: 1px solid #ffffff; /* Green */
        @include tablet-down{
          margin-top: 16px;
          width: 100%;
        }
    }
    margin-bottom: 186px;
}
}
}
</style>
