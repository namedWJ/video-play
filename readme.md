### 基于zepto的视频播放器
包含的元素以及实现的功能

* 视频的播放、暂停
* 全屏显示
* 声音的开关
* 开始结束时间、进度条

### 基于vue的视频播放器

### 一些相关的API
```
<video id="media" src="images/video.mp4"></video>
<script type="text/javascript">
var Media = document.getElementById("media"); 

Media.play(); //播放
Media.pause(); //暂停
Media.currentTime = value; //当前播放的位置，赋值可改变位置
Media.startTime; //一般为0，如果为流媒体或者不从0开始的资源，则不为0
Media.duration; //当前资源长度 流返回无限
Media.paused; //是否暂停
Media.defaultPlaybackRate = value;//默认的回放速度，可以设置
Media.playbackRate = value;//当前播放速度，设置后马上改变
Media.played; //返回已经播放的区域，TimeRanges，关于此对象见下文
Media.seekable; //返回可以seek的区域 TimeRanges
Media.ended; //是否结束，true或者false
Media.autoPlay; //是否自动播放，true或者false
Media.loop; //是否循环播放，true或者false
Media.muted;  //是否静音，也可以赋值true或false设置静音状态
Media.volume //设置音量，最小0，0.5是50%音量，最大1；


//监听事件
var eventTester = function(e){
	Media.addEventListener(e,function(){
		console.log((new Date()).getTime()+'   '+e);
	},false);
}

eventTester("play"); //play()和autoplay开始播放时触发
eventTester("pause"); //pause()触发
eventTester("ended"); //播放结束
eventTester("volumechange"); //音量改变
eventTester("timeupdate"); //播放时间改变
eventTester("loadedmetadata"); //成功获取资源长度
eventTester("playing"); //开始回放
eventTester("loadstart"); //客户端开始请求数据
eventTester("progress"); //客户端正在请求数据
eventTester("suspend"); //延迟下载
eventTester("abort"); //客户端主动终止下载（不是因为错误引起）
eventTester("loadstart"); //客户端开始请求数据
eventTester("progress"); //客户端正在请求数据
eventTester("suspend"); //延迟下载
eventTester("abort"); //客户端主动终止下载（不是因为错误引起），
eventTester("error"); //请求数据时遇到错误
eventTester("stalled"); //网速失速
eventTester("loadeddata"); //
eventTester("waiting"); //等待数据，并非错误
eventTester("canplay"); //可以播放，但中途可能因为加载而暂停
eventTester("canplaythrough"); //可以播放，歌曲全部加载完毕
eventTester("seeking"); //寻找中
eventTester("seeked"); //寻找完毕
eventTester("ratechange"); //播放速率改变
eventTester("durationchange"); //资源长度改变

</script>
```