#player.md

[一个能看很多收费电影的小网站](http://www.yakuhd.com/programs/159129.html)

[这是我弄了半天找到的疑似播放器代码，抽时间研究出来然后他的就是我的](http://vip3.rwjfs.com/tp/js/tp.js)o(*￣▽￣*)ブ

[最简单的基于Flash的流媒体示例：网页播放器（HTTP，RTMP，HLS）](http://blog.csdn.net/leixiaohua1020/article/details/43936415)


影音嗅探器

[流媒体网站制作方法](http://zhidao.baidu.com/link?url=vg7rGQgcaFdvGPn2Cob87fff0UG3MknyywjYzWKP6H9alsxamZkf1k0N0AUkuG_WU-dKSk9_w1QboDz5Mg9JJ_)


[优酷土豆腾讯视频html地址转flash swf地址](http://www.phpddt.com/php/html-to-flashswf.html)


## 获取网络流媒体地址

酷抓网络嗅探器
影音嗅探器

[教你如何获取网络流媒体地址](http://cn.daroonsoft.com/bbs/forum.php?mod=viewthread&tid=66)


## 那么如何在网页中插入swf

swf文件是幻灯片文件，那么如何在网页中插入幻灯片呢？具体的代码如下：
1.最简单的插入方式(经测试可用)：

    <embed src="你的flash地址.swf" width="300" height="220">
2.可以调整的flash文件：

    <param name="movie" value="你的flash地址" ref="">    
    <param name="quality" value="High">    
    <param name="_cx" value="12383">    
    <param name="_cy" value="1588">    
    <param name="FlashVars" value="">    
    <param name="Src" ref="" value="你的flash地址">    
    <param name="WMode" value="Window">    
    <param name="Play" value="-1">    
    <param name="Loop" value="-1">    
    <param name="SAlign" value="">    
    <param name="Menu" value="-1">    
    <param name="Base" value="">    
    <param name="AllowScriptAccess" value="always">    
    <param name="Scale" value="ShowAll">    
    <param name="DeviceFont" value="0">    
    <param name="EmbedMovie" value="0">    
    <param name="BGColor" value="">    
    <param name="SWRemote" value="">    
    <param name="MovieData" value="">    

    </object>