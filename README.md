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
  
20课
