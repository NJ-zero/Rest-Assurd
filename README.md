# Rest-Assurd
Rest-Assurd学习笔记

### 环境搭建
##### 1.JDK 、 maven 、 Intellij IDEA
JDK及maven环境变量配置，请自行百度。
环境配置完成后，输入

mvn -v 

java -version

#####2.新建项目添加依赖

#####2.1首先新建一个maven项目

进入IDEA---File---New---Project---maven

#### 2.2在pom.xml添加相关依赖
在pom.xml中添加rest-assurd、json-path、junit等相关依赖

``````
 <dependencies>
        <!--rest assured相关-->
        <dependency>
        <groupId>io.rest-assured</groupId>
        <artifactId>rest-assured</artifactId>
        <version>3.0.3</version>
        </dependency>

        <dependency>
        <groupId>io.rest-assured</groupId>
        <artifactId>json-path</artifactId>
        <version>3.0.3</version>
        </dependency>

        <dependency>
        <groupId>io.rest-assured</groupId>
        <artifactId>xml-path</artifactId>
        <version>3.0.3</version>
        </dependency>

        <!--junit-->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.12</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
``````    
##### 静态导入
``````
import static io.restassured.RestAssured.*;
import static io.restassured.matcher.ResponseAwareMatcher.*;
import static org.hamcrest.Matchers.*;

``````

新建一个class文件，静态导入这些classes，如果文件不标红，则说明环境搭建成功：
以百度为例，一个简单的demo如下：

``````
public class Demo1 {

    @Test
    public  void test_demo1(){
        int statucecode = get("http://www.baidu.com/").statusCode();
        assertEquals(200,statucecode);
    }
}
``````