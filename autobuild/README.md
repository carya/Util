#autobuild.py

iOS 自动化打包脚本，并上传*ipa*文件至蒲公英。参数说明:

```
Usage: autobuild.py [options]

Options:
  -h, --help            show this help message and exit
  -w name.xcworkspace, --workspace=name.xcworkspace
                        Build the workspace name.xcworkspace.
  -p name.xcodeproj, --project=name.xcodeproj
                        Build the project name.xcodeproj.
  -s schemename, --scheme=schemename
                        Build the scheme specified by schemename. Required if
                        building a workspace.
  -m description, --desc=description
                        Pgyer update description.
```

使用方式:
```
./autobuild.py -p youproject.xcodeproj -s schemename
或者
./autobuild.py -w youproject.xcworkspace -s schemename
```

脚本中有几个全局变量，根据自己项目设置进行修改其值, 包括:

```
CONFIGURATION = "Release"
EXPORT_OPTIONS_PLIST = "exportOptions.plist"
#会在桌面创建输出ipa文件的目录
EXPORT_MAIN_DIRECTORY = "~/Desktop/"
```

*CONFIGURATION*：可在项目工程文件所在目录执行`xcodebuild -list`查看所有可选取值。
*EXPORT_OPTIONS_PLIST*：导出*ipa*文件时的配置参数，该参数值是你的配置参数文件名，请在*autobuild.py*文件所在目录下创建*exportOptions.plist*文件，配置参数可使用`xcodebuild --help`查看所有可选取值。
*EXPORT_MAIN_DIRECTORY*：默认情况下会在桌面创建*ipa*文件导出的文件夹，文件夹命名如:*~/Desktop/{scheme}{2016-12-28_08-08-10}*。

```
# configuration for pgyer
PGYER_UPLOAD_URL = "http://www.pgyer.com/apiv1/app/upload"
DOWNLOAD_BASE_URL = "http://www.pgyer.com"
USER_KEY = "15d6xxxxxxxxxxxxxxxxxx"
API_KEY = "efxxxxxxxxxxxxxxxxxxxx"
#设置从蒲公英下载应用时的密码
PYGER_PASSWORD = "" 
# 蒲公英更新描述
PGYDESC = ""
```
上传*ipa*文件至蒲公英的配置，你需要设置的是:*USER_KEY*, *API_KEY*, *PYGER_PASSWORD*。

相关说明见我的博客[iOS自动打包并发布脚本](http://liumh.com/2015/11/25/ios-auto-archive-ipa/)
