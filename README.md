# PCRBoxRecognizer
使用OpenCV进行角色的自动识别
## 环境
本人使用了python3.6版本，需要依赖的包在requirements.txt中，安装方法`pip install requirements.txt`，也可视情况使用`conda install`指令进行安装，方法不再赘述。
## 函数使用说明
### findTemplateFromSource(source, template, value, width)
        source是查找的图片，template是查找的角色图标，两个参数目前均为传入path即可，函数执行过程中会读取图片（日后会优化为一开始全部读取进内存中）。
        value为检测的阈值，越高越严格，我测试在jjc界面可以设置为0.6。
        width为模板图片需要缩放到的宽度（因为角色头像是正方形所以高度和宽度相等），只有当模板和被搜索图片中的元素大小相近时才能匹配到。
        函数返回值为形如[{'x': 1598.0, 'y': 637.0}, {'x': 1599.0, 'y': 637.0}]的字典数组，内含找到的元素在图片中的位置，位置已由模板左上角修正为模板中心。~~暂未去重。~~已做去重处理。
    