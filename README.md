Some useful utils

#autobuild.py

iOS 自动化打包脚本，使用方式:

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
  -t targetname, --target=targetname
                        Build the target specified by targetname. Required if
                        building a project.
  -o output_filename, --output=output_filename
                        specify output filename
```

脚本中有几个全局变量，根据自己项目设置进行修改其值, 包括:

```
CODE_SIGN_IDENTITY = "iPhone Distribution: xxxxxxxx Co. Ltd (xxxxxxx9A)"
PROVISIONING_PROFILE = "xxxxxxxxxx-xxxxx-xxxxx-xxxx-xxxxxxxxxxxx"
CONFIGURATION = "Release"
SDK = "iphoneos"
```

相关说明见我的博客[iOS自动打包并发布脚本](http://liumh.com/2015/11/25/ios-auto-archive-ipa/)
