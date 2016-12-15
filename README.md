# gradle-jcenter-push
###上传JCenter插件
###参考
https://github.com/nuuneoi/JCenter

https://github.com/chrisbanes/gradle-mvn-push
###变量定义参考gradle-mvn-push，都在gradle.properties与local.properties
###project sample
https://github.com/tingbob/TestLib
###文档指引
http://www.jianshu.com/p/3c63ae866e52

##Project gradle.properties

```properties
VERSION_NAME=0.0.1
GROUP=com.github.tingbob

POM_DESCRIPTION=test lib for Android
POM_URL=https://github.com/tingbob/TestLib
POM_SCM_URL=https://github.com/tingbob/TestLib
POM_SCM_CONNECTION=scm:git@github.com:tingbob/TestLib.git
POM_SCM_DEV_CONNECTION=scm:git@github.com:tingbob/TestLib.git
POM_LICENCE_NAME=The Apache Software License, Version 2.0
POM_LICENCE_URL=http://www.apache.org/licenses/LICENSE-2.0.txt
POM_LICENCE_DIST=repo
POM_DEVELOPER_ID=tingbob
POM_DEVELOPER_NAME=tingbob
POM_DEVELOPER_EMAIL=tingbob@hotmail.com

BINTRAY_REPO=maven
POM_GIT_URL=scm:git@github.com:tingbob/TestLib.git
# 如果有多个协议，逗号隔开，比如ALL_LICENCES=A,B,C
ALL_LICENCES=Apache-2.0
```

##Your upload library gradle.properties
```properties
POM_NAME=TestLib
POM_ARTIFACT_ID=testlib
POM_PACKAGING=aar
```

##Your local properties
```properties
bintray.user=tingbob
bintray.apikey=xxxxxx
bintray.gpg.password=xxxxxx
```
