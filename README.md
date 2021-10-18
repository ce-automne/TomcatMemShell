# TomcatMemShell
拿来即用的Tomcat7/8/9/10版本Listener/Filter/Servlet内存马，支持注入CMD内存马和冰蝎内存马

测试通过的Tomcat版本：  
    tomcat7.0.99(2019-12-17)  tomcat7.0.64(2015-10-14)    tomcat7.0.34(2012-12-11)  
    tomcat8.5.69(2021-07-05)    tomcat8.0.46(2017-08-18)  
    tomcat9.0.12(2018-09-10)    tomcat9.0.53(2021-09-10)  
    tomcat10.0.11(2021-09-10)   tomcat10.1.0-M2(2021-07-02)
# 说明
### JSP目录
根据目标环境上传对应大版本的.jsp文件并访问，访问后页面返回>@<即说明注入成功，支持Tomat7/8/9/10版本

见名知义，memlistener8910.jsp表示适用于Tomcat8/9/10版本的Listener CMD内存马，icememfilter7.jsp表示适用于Tomcat7版本的Filter冰蝎内存马

### DeSerialize目录
对应的.java文件和.class文件需要结合反序列化漏洞类型进行漏洞利用，如fastjson的jndi或snakeyaml的spi等，支持Tomcat8/9/10版本

不适用于shiro漏洞，shiro漏洞利用需要继承AbstractTranslet类并且修改Header大小，感兴趣的可参考该项目：https://github.com/KpLi0rn/ShiroVulnEnv

见名知义，LRain10表示适用于Tomcat10版本的Listener CMD内存马，IFRain表示适用于Tomcat8/9的Filter冰蝎内存马 （注意java文件修改文件名请与类名保持一致）

对应java文件中standardContext的获取依据Litch1师傅《基于全局储存的新思路 | Tomcat的一种通用回显方法研究》的Thread.currentThread().getContextClassLoader()方式，该方式不适用于Tomcat7

# 用法
**Listener型/Filter型:**  
        CMD内存马URL：xx.xx.xx.xx/?chan=whoami  
        冰蝎内存马URL：xx.xx.xx.xx/                     冰蝎连接密码：goautomne

**Servlet型：**  
        CMD内存马URL: xx.xx.xx.xx/p?chan=whoami  
        冰蝎内存马URL: xx.xx.xx.xx/p        冰蝎连接密码：goautomne

# 参考链接

https://mp.weixin.qq.com/s?__biz=MzIwNDA2NDk5OQ==&mid=2651374294&idx=3&sn=82d050ca7268bdb7bcf7ff7ff293d7b3

# 免责声明
仅供技术研究，请勿用于非法用途

