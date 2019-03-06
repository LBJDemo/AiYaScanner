# AiYaScanner
:fire: zxing and zbar combined with scan code.  只为真正的 zxing zbar 结合二维码扫描：https://github.com/nanchen2251/AiYaScanner

TODO：
1. 剥离 zxing（已完成）；
2. 优化 zxing 预览和解码（已完成）；
3. 加入 zbar 解码（已完成）；
4. 兼容优化；（部分完成）；
5. 二维码放大缩小(已完成)；
6. 目前解码为了兼容，是串行的，相反拖长了时间，后面会改成并行的。
7. 自动放缩；
8. 目前为了速度，**仅支持二维码**，后面暴露接口支持其他格式；

**更多有效的优化，请大家一起来提 PR！**
**有任何需求或者 BUG,请提 issues！**


## 效果图<br>
![](https://github.com/nanchen2251/AiYaScanner/blob/master/screenshot/screenshot.gif)

#### ⊙开源不易，希望给个 star 或者 fork 奖励
#### ⊙拥抱开源：https://github.com/nanchen2251/
#### ⊙交流群（拒绝无脑问）：118116509 <a target="_blank" href="//shang.qq.com/wpa/qunwpa?idkey=e6ad4af66393684e1d0c9441403b049d2d5670ec0ce9f72150e694cbb7c16b0a"><img border="0" src="http://pub.idqqimg.com/wpa/images/group.png" alt="Android神技侧漏交流群" title="Android神技侧漏交流群"></a>( 点击图标即可加入 )<br>

## 特点
  1、只为极速扫码而生。<br>
  2、默认只支持二维码扫描。<br>
  3、支持双击放大缩小。<br>
  4、支持多指放大缩小。<br>
## 使用方法
#### 1、添加依赖<br>
##### Step 1. Add it in your root build.gradle at the end of repositories:
```java
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```
##### Step 2. Add the dependency
```java
dependencies {
	        implementation 'com.github.nanchen2251:AiYaScanner:1.0.7'
	}
```
#### 2、在Activity里面使用<br>
```java
   // 必须自己先申请相机和存储权限
   CaptureActivity.startForResult(MainActivity.this, 1024);
   
   @Override
    protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if (resultCode == RESULT_OK && requestCode == 1024 && data != null) {
            String result = data.getStringExtra("result");
            Toast.makeText(getApplicationContext(), "扫码结果：" + result, Toast.LENGTH_SHORT).show();
        }
    }
```
#### 3、你也可以自己编写你的扫一扫 UI
```
// Activity 请继承于 BaseCaptureActivity
// 你也可以不继承，但记得编写相关方法
```

该项目参考了：

* [https://github.com/zxing/zxing](https://github.com/zxing/zxing) 
* [https://github.com/ZBar/ZBar](https://github.com/ZBar/ZBar)

### 关于作者
    南尘<br>
    四川成都<br>
    [其它开源](https://github.com/nanchen2251/)<br>
    [个人博客](https://nanchen2251.github.io/)<br>
    [简书](http://www.jianshu.com/u/f690947ed5a6)<br>
    [博客园](http://www.cnblogs.com/liushilin/)<br>
    交流群：118116509<br>
    欢迎投稿(关注)我的唯一公众号，公众号搜索 nanchen 或者扫描下方二维码：<br>
    ![](https://github.com/nanchen2251/Blogs/blob/master/images/nanchen12.jpg)


#### 有码走遍天下 无码寸步难行（引自网络）

> 1024 - 梦想，永不止步!  
爱编程 不爱Bug  
爱加班 不爱黑眼圈  
固执 但不偏执  
疯狂 但不疯癫  
生活里的菜鸟  
工作中的大神  
身怀宝藏，一心憧憬星辰大海  
追求极致，目标始于高山之巅  
一群怀揣好奇，梦想改变世界的孩子  
一群追日逐浪，正在改变世界的极客  
你们用最美的语言，诠释着科技的力量  
你们用极速的创新，引领着时代的变迁  
  
------至所有正在努力奋斗的程序猿们！加油！！  
    
## Licenses
```
 Copyright 2019 nanchen(刘世麟)

 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
```
