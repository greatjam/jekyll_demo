#DOUAdvertisementKit#

##功能简述##

* 定期获取广告数据，下载广告对应的内容图片
* 定期上传广告操作记录
* 提供一个展示开机广告的UIViewController，可直接使用

##配置##

1. 把DOUAdvertisementKit.xcodeproj拖入项目
2. 打开Target的Build Phases，在Target Dependencies里加入DOUAdvertisementKit,在Link Binary With Libraries里加入libDOUAdvertisementKit.a
3. 在search header path里加入source文件夹的路径
4. 如果你的项目已经import了DOUFoundation,DoubanObjCClient或者DoubanObjCFileManager，要在DOUAdvertisementKit的Target的Build Phases里删掉相应的lib
5. 把DOUAdvertisementKit里的ADStandardResourse.bundle加入项目。另创建一个ADCustomResourse.bundle加入项目，并把应用相应的appbg@2x.png,appbg-568@2x.png加进去。

##使用方式##

1. 直接使用DOUSplashADViewController展示开机广告,Demo里有示例
2. 通过DOUAdvertiseCenter获取DOUAdvertisem
 
	```
	/* 更新数据 */
	-(void)startDataSync;
	
	/* 获取广告 */
	-(DOUAdvertisement *)pickStartUpAdvertisement;
	-(DOUAdvertisement *)pickNormalAdvertisement;
	- (UIImage *)imageForAdvertisement:(DOUAdvertisement *)ad;
	
	/* 记录数据 */
	- (void)displayedAdvertisement:(NSString *)adId;
	- (void)clickedAdvertisement:(NSString *)adId; 
	```

 
 