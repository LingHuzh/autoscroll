<template>
  <div class="home">
    <div class="main">
			<div id="mm">
				<ul>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				<li><img src="https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1590074609&di=7f2bf025ebad1233899642cf7dbd185d&src=http://a3.att.hudong.com/14/75/01300000164186121366756803686.jpg"/></li>
				</ul>
			</div>
		</div>
  </div>
</template>

<script>
import "../js/jquery-1.7.2.min.js"
$(function () { 
  console.log(666)
 })
window.onload = function() {
  var mm = document.getElementById("mm");
  //复制一份图片内容
  mm.innerHTML = mm.innerHTML + mm.innerHTML;
  var a = autoscroll();
  document.getElementsByClassName("main")[0].onmouseover = function() {
    clearInterval(a);
    setInterval(function() {
      var r = parseInt(Math.random() * 256);
      var g = parseInt(Math.random() * 256);
      var b = parseInt(Math.random() * 256);
      document.getElementsByClassName("main")[0].style.borderColor =
        "rgb(" + r + "," + g + "," + b + ")";
    }, 800);
  };

  document.getElementsByClassName("main")[0].onmouseout = function() {
    a = autoscroll(); //这里不要加var
  };
};

function autoscroll() {
  var v = 1;
  var auto = setInterval(function() {
    //获取mm距离左边界的距离
    var l = mm.offsetLeft;
    //设置mm的css样式
    if (l < -1200) {
      mm.style.left = 0 + "px";
    } else {
      mm.style.left = l - v + "px";
    }
  }, 8);
  return auto;
}

export default {
  name: "Home",
  components: {
    created() {
      this.demo();
    },
    methods: {
      demo() {
        var o = 1;
        console.log(o);
      }
    }
  }
};
</script>
<style lang="scss" scoped>
@import url("../style/base.css");
ul,li{margin: 0; padding: 0; list-style: none;}
			.main{ width: 1040px;height: 380px; overflow: hidden; position: relative;  margin: 0px auto; border: 30px ridge;border-color: rgb(255,255,0); }
			#mm{ width: 5000px; position: absolute; left:0}
			#mm ul li{ float: left;}
			#mm ul li img{ width: 260px;height: 380px;}
</style>
