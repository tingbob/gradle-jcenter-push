# gradle-jcenter-push
###Upload JCenter plugin
###Reference and English docs
https://github.com/nuuneoi/JCenter

https://github.com/chrisbanes/gradle-mvn-push
###Chinese doc guide for nuuneoi
http://www.jianshu.com/p/3c63ae866e52
####Parameters definition is similar to gradle-mvn-push. The global parameters are located in gradle.properties and local.properties
###Project sample
https://github.com/tingbob/TestLib
###Project gradle.properties

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
# If you have multiple protocal, 
# you should define like this: ALL_LICENCES=A,B,C
ALL_LICENCES=Apache-2.0
```

###Your upload module library gradle.properties
```properties
POM_NAME=TestLib
POM_ARTIFACT_ID=testlib
POM_PACKAGING=aar
```

###Your local properties
```properties
bintray.user=tingbob
bintray.apikey=xxxxxx
# If you want to upload to Maven Central
bintray.gpg.password=xxxxxx
```
###Your project build.gradle
```properties
buildscript {
    ......
    dependencies {
        classpath 'com.android.tools.build:gradle:2.2.3'
        classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.7.3'
        classpath 'com.github.dcendents:android-maven-gradle-plugin:1.5'

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
    ......
}

allprojects {
    version = VERSION_NAME
    group = GROUP
    ......
}
```

###Your upload module build.gradle
```properties
apply from: 'https://raw.github.com/tingbob/gradle-jcenter-push/master/gradle-jcenter-push.gradle'
```
###Terminal command line
####Check the package validity
./gradlew install
####Upload to JCenter
./gradlew bintrayUpload
#Enjoy
