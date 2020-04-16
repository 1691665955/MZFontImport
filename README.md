# MZFontImport

## 前言
在iOS开发过程中，我们有时会需要使用一些炫酷或特定字体，那么就需要导入三方自定义字体来实现功能。
## 下载自定义字体
对应的字体请自行百度下载，***目前大部分字体商用均需获取授权，请注意不要侵权使用***
## 导入自定义字体
1. 将字体文件拖入工程  
![image](http://upload-images.jianshu.io/upload_images/5912495-6398ee4ffd700ff7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2. 在Info中添加***Fonts provided by application***选项，并添加子项，填入你导入的自定义字体名称，我这里填入let.ttf  
![image](http://upload-images.jianshu.io/upload_images/5912495-3796164e23af642e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3. 找到对应的字体名称
- 本地打开字体库文件，查看标题上的字体库名称  
![image](http://upload-images.jianshu.io/upload_images/5912495-b0d4d39518f90138.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 使用代码找到对应的字体family和name
```
    for (NSString *fontFamilyName in [UIFont familyNames]) {
        NSLog(@"family:'%@'\n",fontFamilyName);
        for (NSString *fontName in [UIFont fontNamesForFamilyName:fontFamilyName]) {
            NSLog(@"\tfont:'%@'\n",fontName);
        }
        NSLog(@"-------------\n");
    }
```
- 查看log搜索我们在本地打开字体库时标题上的字体库名称（Let's go Digital），找到对应的字体名称（LetsgoDigital-Regular）  
![image](http://upload-images.jianshu.io/upload_images/5912495-a78fcb5bbaea80b6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
4. 使用对应的Font
```
    UILabel *label = [[UILabel alloc] initWithFrame:CGRectMake(20, 100, self.view.bounds.size.width-40, 50)];
    label.text = @"asdff443434";
    label.textColor = [UIColor blackColor];
    label.textAlignment = NSTextAlignmentCenter;
    label.font = [UIFont fontWithName:@"LetsgoDigital-Regular" size:40];
    [self.view addSubview:label];
```

![image](http://upload-images.jianshu.io/upload_images/5912495-ebdf82abac69ada4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5. 附上[demo](https://github.com/1691665955/MZFontImport.git)链接
