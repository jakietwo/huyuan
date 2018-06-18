<template>
  <div class="huyuan">
    <audio id="audio" style="display: none;height: 0" autoplay="autoplay" controls autobuffer>
      <source id="audioSource" src="@/assets/music/0.mp3"/>
    </audio>
    <div class="text">Happy Birthday To<br/> HuYuan <br/>胡语安 <br/>永远十八 </div>
    <div ref="wrapper" class="wrapper">
      <div>
        <div id="avatar">
          <transition name="slide">
            <img class="img" id="img" src="@/assets/love/2.jpg">
          </transition>
        </div>
      </div>
    </div>


  </div>
</template>

<script>
  import music1 from '@/assets/music/1.mp3'
  import music2 from '@/assets/music/2.mp3'
  import dancehall from '@/assets/music/Dancehall.mp3'
  import onecallway from '@/assets/music/onecallway.mp3'
  import azhen from '@/assets/music/azhen.mp3'
  import img1 from '@/assets/love/1.jpg'
  import img2 from '@/assets/love/3.jpg'
  import img3 from '@/assets/love/4.jpg'
  import img4 from '@/assets/love/5.jpg'
  import img5 from '@/assets/love/6.jpg'
  import img6 from '@/assets/love/7.jpg'
  import img7 from '@/assets/love/8.jpg'
  import img8 from '@/assets/love/9.jpg'
  import img9 from '@/assets/love/10.jpg'
  import img10 from '@/assets/love/11.jpg'
  import img11 from '@/assets/love/12.jpg'
  import img12 from '@/assets/love/13.jpg'
  import img13 from '@/assets/love/14.jpg'
  import img14 from '@/assets/love/15.jpg'
  import img15 from '@/assets/love/16.jpg'
  import img16 from '@/assets/love/17.jpg'
  import img17 from '@/assets/love/18.jpg'
  import img18 from '@/assets/love/19.jpg'
  import img19 from '@/assets/love/20.jpg'
  import img20 from '@/assets/love/21.jpg'
  import img21 from '@/assets/love/22.jpg'
  import img22 from '@/assets/love/23.jpg'
  import img23 from '@/assets/love/24.jpg'
  import img24 from '@/assets/love/25.jpg'
  import img25 from '@/assets/love/26.jpg'

  export default {
        name: "home",
        data() {
            return {
              size: 375,
              current: 0,
              imageList: [
                img1,img2,img3,img4,img5,img6,img7,img8,img9,img10,img11,
                img12,img13,img14,img15,img16,img17,img18,
                img19,img20,img21,img22,img23,img24,img25
              ],
              imageIndex: 0
            }
        },
        mounted(){
          let vm = this;
          console.log(this.imageList[0]);
          let audio = document.getElementById('audio');
          audio.addEventListener('play', function () {
            console.log('播放ing');
          });
          let img = document.getElementById('img');
          let i = 1;
          setInterval(()=>{
            if (i>=26){
              i=0;
            }
            img.src = this.imageList[i];
            i++;
          },30000);
          audio.addEventListener('ended',function () {
            let audioSource = document.getElementById('audioSource');
            if (vm.current === 0){
              audioSource.src = music1;
            }else if (vm.current === 1){
              audioSource.src = music2;
            }else if (vm.current === 2){
              audioSource.src = dancehall;
            }else if(vm.current === 3){
              audioSource.src = onecallway;
            }else if (vm.current === 4){
              audioSource.src = azhen;
            }
            else {
              vm.current = -1;
            }
            vm.current ++;

            audio.load();
            audio.play();
          })
        },
        methods:{

        }
    }
</script>

<style lang="stylus" scoped>
  .huyuan
    background linear-gradient(to bottom ,pink,		lightpink)
    width 100vw
    height 100vh
    .text
      font-size 24px
      padding-top 5%
      margin 0 auto
      text-align center
    .wrapper
      position absolute
      width 100%
      overflow hidden
      #avatar
        margin-top 10%
        width 100vw
        height 100vw
        border-radius 50vw
        animation rotate 60s linear infinite
        .img
          width 100%
          height 100%
          border-radius 50%
          background-repeat no-repeat
  @keyframes rotate{
      from{
        transform rotate(0deg)
      }
      to{
        transform rotate(360deg)
      }
  }

</style>
