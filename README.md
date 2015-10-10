# tubatu-viewpager
这是高仿土巴兔选择装修风格的效果的Android版本，IOS版本请点击这里[tubatu-iCarousel](https://github.com/hanhailong/tubatu-iCarousel)，这里通过自定义ViewPager来实现，为什么通过ViewPager来实现呢，一是ViewPager很容易实现切换动画效果，二是选择的那一项自动居中

# 效果图
![image](http://img.blog.csdn.net/20150928093108444)

# 修改bug

2015-10-10号修复sdk4.4之下viewpager子view重叠的bug，重叠的原因是父布局没有重新绘制，只需要在transformPage(View page, float position)方法中添加一行代码：

``
if (Build.VERSION.SDK_INT < Build.VERSION_CODES.KITKAT) {
            page.getParent().requestLayout();
        }
``

