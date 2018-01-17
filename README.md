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
	
然后就可以使用了。
