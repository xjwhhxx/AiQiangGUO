AiQiangGUO Ai强国 基于Autojs实现的模拟点击学习强国辅助工具 适配安卓

感谢：基于Auto.js_4.1.1 Alpha2运行框架 原始代码基于@ivanwhaf xxqg-helper UI版本 文章基于播报按钮进行判断点击来自@chongyadong 争上游基于题目对比答题来自@Ivan-cn 另有部分代码移植自@lolisaikou，感谢各位开发同仁一起解决各种问题。

注意&声明:20201229 1,严禁使用本代码收费代挂机，严禁收费传播。
                  2,本代码允许再次修改，但严禁修改时加入恶意代码，严禁未经修改核心代码核心逻辑即进行加密。
                  3，再次修改请注明来源 修改作者，请同时修改版本号以示区别。 
                  4,使用风险自担(包括且不限于封号，警告，喝茶)。 
                  5，本代码仅保证本人发布版本无恶意代码。
                  
权限说明如下:悬浮窗(弹出运行日志)，无障碍(模拟点击与滑动)，存储(日志输出与数据库读写)。其他权限由autojs申请，均可拒绝。

程序设计理念：正常跑完全流程不跑飞 不卡死 不死循环，得每天固定分数。
            它是一个辅助工具，从每天的手动重复性点击中解放出来。
            它不是一个答题工具，不以 答题全对 争上游 双人得第一 为目标。
            因此，本程序有概率出现 每周 专项答题不能全对浪费分数，争上游 双人不能满分。
            
网盘链接蓝奏云 https://wws.lanzous.com/b01npbw7a 密码:263a
注：近期蓝奏云网盘解析问题，链接如打不开请尝试https://wws.lanzoui.com/b01npbw7a 或者https://wws.lanzoux.com/b01npbw7a 

执行逻辑为： 文章 12篇30秒（含前2篇文章分享点赞评论），视频 6个60秒，本地频道，挑战答题 1轮*5题，每日答题（至领取奖励已达今日上限），之后循环检查 文章个数时长积分、视频个数积分，本地，挑战，每日答题 积分，不足则循环执行。 以上足够之后，检查分享评论积分，不足则学习2篇文章执行分享点赞评论；检查视频时长，不足则收听广播补时长（注意广播不会自动退出，但不影响接下来执行）；检查双人对战积分，<1执行一次双人对战；检查争上游答题积分，<2执行两次争上游答题。

目前仍存在问题：文章 视频重复点击，导致积分始终不足而循环执行。

词形与注音题格式为 题目去除空格，带句号，紧跟第一选项。 示例如下: 选择词语的正确词形。一愁莫展

20210116 v2.19 20210116 推荐更新。更新日志：修正部分手机的本地频道控件变化导致的本地频道点击错误；修正我的页面 我要答题文本不可点击导致的所有答题卡在我的页面，点击其父控件。

20210115 v2.19 20210115 推荐更新。更新日志：修正强国 对战入口变化导致的双人对战不能进入问题，加入邀请好友与随机匹配，代码使用随机匹配。/蓝奏云外发版本号标识为v2.19 20210125，汗一个

20201225 v2.19 20201225 推荐更新。 更新日志：修正强国 争上游 对战界面变化导致的不能答题问题，感谢@KB64ba同学慧眼发现，距离答题结束 删除。

20201215 v2.19 20201212 推荐更新。 更新日志: 修正题库已知错题。 修改词形题与注音题答题逻辑，对应修改题库内格式。 修正双人对战连续答题逻辑。 跟随强国APP升级电台收听逻辑。 修改题目输出日志与题库实际搜索一致。 加入运行日志输出功能，默认/脚本/AiQiangGuo日志.txt。

20201028 使用Ivan-cn处理挑战答题的逻辑：随机点击，如果正确，写入题库。 挑战答题支持自定义次数和题数，所以可以用来挂机刷题库。 增加争上游答题次数自定义，双人对战次数=争上游次数-1，因不容易判断答题错误，故该部分未加入随机点击正确写入题库功能。

20201017 加入挑战答题分享复活功能， 完善部分争上游 对战答题逻辑。

原始版本说明 0，源代码基于https://github.com/ivanwhaf/xxqg-helper V3.1.3 UI版本进行修改而来。 1，修改学习按钮点击方式，由基于文本"学习"（强国改版后为“工作”）改为基于控件"home_bottom_tab_button_work"点击。 2，积分执行加入循环判断，引入顺序执行（因测试部分手机积分获取时返回Null，获取不到积分）。 3，部分手机本地频道控件位置为13，故引入基于是否存在"切换地区"的判断。 4，文章视频使用随机数（随机1 2 3文章点击推荐 要闻 综合，视频点击第一频道 学习视频 联播频道）。 5，计划加入：挑战答题不足1轮5题 失败时的分享复活。 6，存在问题：文章 视频重复点击；文章有概率点击到广播，然后不能自动执行，需手动返回学习主页（执行逻辑将文章优先执行后已降低此问题概率）。

