app.json
属性
1. pages / String Array / 设置页面路径
  (1) 路径 + 文件名 / pages/index/index
  (2) 每次增删页面 都要修改
2. windiow / Object / 默认页面的窗口表现
  (1) navigationBarBackgroundColor / 
  (2) navigationBarTextStyle / 导航栏标题颜色
  (3) navigationBarTitleText / 标题文字内容
  (4) backgroundColor / 窗口的背景色
  (5) backgroundTextStyle / 下拉背景字体、loading图的样式
  (6) enablePullDownRefresh / 是否开启下拉刷新
  (7) onReachBottomDistance / 页面上拉触底距页面底部距离
3. tabBar / Object / 底部tab的表现
  (1) color / 文字默认颜色
  (2) selectedColor / 选中的颜色
  (3) backgroundColor / 背景色
  (4) borderStyle / 边框的颜色
  (5) list / 数量
  (6) position / 可选bottom top
4. networkTimeout / Object / 网络超时时间
5. debug / Boolean / 是否开启debug模式

page.json
属性
1. navigationBarBackgroundColor / 
2. navigationBarTextStyle / 
3. navigationBarTitleText / 
4. backgroundColor / 
5. backgroundTextStyle / 
6. enablePullDownRefresh
7. onReachBottomDistance 
8. disableScroll / 只能在page生效

WXML页面文件 (WeiXin Markup Language)
1. {{}} / 数据绑定
  (1) 内容绑定 <view>{{message}}</view>
  (2) 组件属性绑定 <view id="item-{{news}}"></view>
  (3) 控制属性绑定 <view wx:if="{{condition}}"></view>
  (4) 关键字绑定 <checkbox checked="{{false}}"></checkbox>
  (5) 绑定内进行计算
    - 三元运算 / <view hidden="{{flag?true:false}}">Hidden</view>
    - 算术运算 <view>{{a+b}} + {{c}} +d</view>
    - 逻辑运算 <view wx:if="{{length > 5}}"></view>
    - 字符串运算 <view>{{"hello" + name}}</view>
    - 数据路径运算 <view>{{object.key}}{{array[0]}}</view>
2. wx:if 条件渲染
  (1) 语句 wx:if="{{condition}}"
  (2) wx:if / wx:elif / wx:else
  (3) <block> 不是组件 仅仅是包装元素 仅仅接受控制属性
  (4) wx:hidden 全局渲染
3. wx:for 列表渲染
  (1) wx:for="{{array}}" 绑定数组
  (2) index 下标 / item 元素
  (3) wx:for-item , wx:for-index
4. <template/> 模版
  (1) 定义模板 name="~" 
  (2) 使用模版 is="name"
5. 事件
  (1) 事件 绑定 以key value的形式呈现
  (2) key以catch和bind开头
  (3) value对应page中定义的同名函数
  (4) WXML有6个冒泡事件
    - touchstart
    - touchmove
    - touchcancel
    - touchend
    - tap
    - longtap
6. 引用
  (1) 提供两种文件引用方式 import 和 include
  (2) import 只能单向
  (3) include 整个代码代入
  
app.js
1. onLaunch / 小程序初始化完成后 会触发并只会触发一次
2. onShow / 启动 或者 后台切换到前台 则会触发
3. onHide / 前台切换到后台 则会触发

页面.js
1. 初始化数据 / data属性
2. 生命周期函数
  (1) onLoad / 加载完调用该函数
  (2) onShow / 显示时调用该函数
  (3) onReady / 初次渲染完成调用该函数
  (4) onHide / 隐藏时调用该函数
  (5) onUnload / 卸载时调用该函数
  (6) onPullDownRefresh / 下拉刷新时调用该函数
3. 事件处理函数
4. 使用setData修改初始化数据
  - this 代表本页面 

WXSS样式文件 
1. id选择器
2. class选择器
3. 新的尺寸单位 rpx
  - 规定屏幕宽为750rpx
4. 外联样式 @import

组件
- 封装了HTML5的元素

视图容器
1. view
  (1) hover-class / String / 指定按下去的样式类
  (2) hover-stop-propagation / Boolean / 是否阻止本节点的祖先节点出现点击态
  (3) hover-start-time / Number / 按住多久出现点击态
  (4) hover-stay-time / Number / 手指松开后点击态保留时间
2. scroll-view
  (1) scroll-x 
  (2) scroll-y  
  (3) upper-threshold / 距离顶部/左边多远 触发事件
  (4) lower-threshold / 距离底部/右边多远 触发事件
  (5) scroll-top / 设置竖向滚动条的位置
  (6) scroll-left / 横向滚动条的位置
  (7) scroll-into-view / 设置哪个方向可滚动
  (8) scroll-with-animation
  (9) enable-back-to-top / 手机点击顶部 触发事件
  (10) bindscrolltoupper / 滚动到底部/左边 触发事件
  (11) bindscrolltolower / 滚动到底部/右边 触发事件
  (12) bindscroll / Eventhandler 类型
 3. swiper
  (1) indicator-dots / 是否显示面板指示点
  (2) indicatior-color / 设置指示点的颜色
  (3) indicator-active-color / 当前选中的知识点颜色
  (4) autoplay / 是否自动切换
  (5) currect / 当前所在页面的index索引
  (6) interval / 自动切换时间间隔
  (7) duration / 滑动动画的时长
  (8) circular / 采用衔接滑动
  (9) veritical / 滑动方向是否为纵向
  (10) Bindchange / current改变时触发的事件
  
 基础内容组件
 1. icon
    属性 
    (1) type: success, success_no_circle, info, warn, waiting, cancel, download, search, clear
    (2) size
    (3) color
 2. text组件
    默认文本在同一行 支持转义字符 换行 空格等
    属性
    (1) selectable / 文本是否可选
    (2) space / 显示连续空格 false&ture / ensp, emsp, nbsp
    (3) decode / 对文本解码
 3. Progress组件
    (1) percent / 进度的百分比
    (2) show-info / 显示百分比
    (3) stroke-width / 进度条的宽度
    (4) color 
    (5) activeColor 
    (6) backgroundColor / 未选择的颜色
    (7) active 有无动画
    (8) active-mode / 动画的播放模式 / backwards & forwards
 
 表单组件
 1. button
    (1) size
    (2) type / primary default warn
    (3) plain / 是否镂空
    (4) disabled
    (5) loading
    (6) form-type / submit & reset
    (7) open-type / contact & share & getUserInfo & getPhoneNumber
    (8) hover-class
    (9) hover-step-propagation
    (10) hover-start-time
    (11) hover-stay-time
    (12) bindgetuserinfo / handler属性 返回用户信息 等同wx.getUserInfo
 2. checkbox
    (1) checkbox-group / 多项选择 / bindchange 触发change事件
    (2) 有四个属性
      - value
      - disabled
      - checked
      - color
    (3) e.detail.value
 3. radio
    (1) radio-group / 单项选择 / bindchange 触发change事件
    (2) 属性
      - value
      - disabled
      - checked
      - color
    (3) e.detail.value
 4. input 
    (1) value / 初始内容
    (2) type / text & number & idcard & digit (带小数点)
    (3) password
    (4) placeholder
    (5) placeholder-style
    (6) placeholder-class
    (7) disabled
    (8) maxlength
    (9) auto-focus
    (10) focus
    (11) confirm-type / 右下角文字 / send & search & next & go & done
    (12) confirm-hold
    (13) bindinput 
    (14) bindfocus
    (15) bindblur
    (16) bindconfirm
  5. textarea
    (1) value / 初始内容
    (2) placeholder
    (3) placeholder-style
    (4) placeholder-class
    (5) disabled
    (6) maxlength
    (7) auto-focus
    (8) focus
    (9) auto-height
    (10) show-confirm-bar
    (11) bindfocus
    (12) bindblur
    (13) bindlinechange
    (14) bindinput
    (15) bindconfirm
  6. label
    只有一个属性 for / 绑定控件
  7. picker
    (1) 普通选择器 / mode = selector
      - range
      - range-key
      - value
      - bindchange
      - disabled
    (2) 多项选择器 / mode = multiSelector
      - range / 多维数组
      - range-key
      - value
      - bindchange
      - disabled
    (3) 时间选择器 / mode = time
      - value
      - start
      - end
      - bindchange
      - disabled
    (4) 日期选择器 / mode = date
      - value 
      - start
      - end
      - fields
      - bindchange
      - disabled
    (5) 省市区选择器 / mode = region
      - value
      - custom-item
      - bindchange
      - disabled
  8. picker-view
    (1) picker-view
      - value
      - indicator-style / 选中框
      - indicator-class
      - mask-style
      - mask-class
      - bindchange
    (2) pick-view-column
  9. slider
    (1) min
    (2) max
    (3) step
    (4) disabled
    (5) value
    (6) color
    (7) bindchange
  10. switch
    (1) checked
    (2) type
    (3) bindchange
    (4) color
  11. form
    (1) report-submit
    (2) bindsubmit
    (3) bindreset

导航组件
1. navigator 组件
  (1)
