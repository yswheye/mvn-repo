# mvn-repo   
---
建立自己的依赖库仓库    

## 用法  
1.在项目的根目录build.gradle添加maven仓库地址

	allprojects {
	    repositories {
	        maven { url 'https://raw.githubusercontent.com/yswheye/mvn-repo/master' }
	    }
    }

2.在用到的lib下的build.gradle添加依赖  

	implementation 'com.android.common:common-lib:0.0.1@aar'
	
3.common-lib中添加的依赖要在第二步添加依赖的地方重新添加，因为aar中的代码不包括引用的依赖库。 
	
	api "com.android.support:support-v4:${rootProject.ext.android.supportVersion}"
    api "com.android.support:cardview-v7:${rootProject.ext.android.supportVersion}"
    api "com.android.support:appcompat-v7:${rootProject.ext.android.supportVersion}"
    api "com.android.support:design:${rootProject.ext.android.supportVersion}"
    // rx, retrofit
    api 'com.squareup.retrofit2:retrofit:2.2.0'
    api 'com.squareup.retrofit2:retrofit-converters:2.2.0'
    api 'com.squareup.retrofit2:converter-gson:2.2.0'
    api 'com.squareup.retrofit2:adapter-rxjava:2.2.0'
    api 'com.squareup.okhttp3:okhttp:3.6.0'
    api 'io.reactivex:rxandroid:1.2.1'
    // glide
    api 'com.github.bumptech.glide:glide:3.7.0' 

然后就可以使用了。  

**latest.release 的话会获取到最新的正式版本  
latest.integration会获取到最新的版本，可能是正式版本，也可能是测试版本**
