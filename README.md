# hzr-s-Workplace
一、音乐
1.开场音乐
《战歌》 原名‘不做大锅’，很奇怪吧hhh。 因为在故事背景里，朵菲是一个即将上战场，和变异生物战斗的仿生机器人。  从玩家的视角，这时候并不知道朵菲的真实身份。因此，放一个单纯的战歌比较合适。
2.Boss战音乐
《战歌》 同上，可以呼应一下？（其实就是不想再找一个了hhhh
3.结束音乐
《Cut in love》 又名《木偶的死亡舞步》，曾经被误认为《Dance to the Death》。
如果朵菲杀掉了哥哥，这个bgm可不是庆祝的哦。暗示‘事情远没有那么简单’。 ——《木偶的死亡舞步》。
如果朵菲选择不变异，最终和哥哥和解。那就是《Dance to the Death》
4.游戏循环音乐（待补充）

二、音效
在我们的游戏里，目前只看到了攻击的音效。所以找了4个攻击的音效放在里面。

三、代码
Android实现播放音乐非常简单

private fun initMediaPlayer(){
        val assetManager=assets
        //这里需要把音乐都放在新建的assets文件夹里面。在《第三行代码》里有很详细的描述
        val fd=assetManager.openFd("mixkit-air-in-a-hit-2161.wav")
        mediaPlayer.setDataSource(fd.fileDescriptor,fd.startOffset,fd.length)
        mediaPlayer.prepare()
    }
}

class MainActivity : AppCompatActivity() {
    private val mediaPlayer=MediaPlayer()
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        setSupportActionBar(toolbar)
        //初始化播放器
        initMediaPlayer()
        ceshi.setOnClickListener(){
            if(!mediaPlayer.isPlaying){
                mediaPlayer.start()
            }
        }
    }
