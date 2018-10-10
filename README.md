# WEBTes[WEB端自动化]

一、简介：

1、使用java+webdrver+testng框架，支持firefox、chrome、ie浏览器

2、使用PO分层原理，将页面元素和界面操作分开保存，页面变化只需更改单个元素即可

3、使用log4j记录测试日志，并自动生成html测试报告

4、部署在jenkins上自动构建任务，开展测试


二、框架组成：

1.常用工具类：#driver启动类及元素查找、常用api二次封装、常用工具类（监听器、随机数、断言等等）

src\main\java\Tools目录下：

①BaseDriver driver启动类配置，支持Chrome/Firefox/IE主流浏览器

②BaseAction 对常用的api操作进行二次封装，添加日志记录和元素非空处理，增加代码健壮性

③Element   对FindElement函数进行二次封装，支持智能等待，保证元素查找的稳定性

④Assert    对断言进行二次封装，制定个性化断言方法

⑤ScreenShot 支持实时截图，保留测试数据

⑥MyLisenter 对testng监听器进行重构，增加个性化测试报告

⑦Logger    引入log4j日志管理，记录每一步执行日志，方便追踪定位

⑧Tool      重写了随机数、时间、文件、Excel表格处理、文件上传等常用工具类

2.脚本管理:#页面元素类、页面操作及逻辑处理

PageElement目录下：

每个页面单独新建一个元素类，使用静态字段管理页面元素，实现元素与业务逻辑的分离

PageAction目录下：

每个页面单独写一个逻辑操作类，将页面的每个动作进行封装，提高代码的重复利用率

3.用例管理：#针对单个测试点的数据驱动用例、针对流程测试的用例（使用testng.xml控制用例执行）

Test_Case目录下：

按业务操作步骤组装测试用例，支持testng数据驱动测试和自定义参数测试

Test_Suit目录下：

按业务流程组装测试套件，测试业务流程，支持参数的全局调用

三、测试结果：#生成漂亮的可视化报告，可查看测试截图和错误日志，支持邮件发送 

[TestReport目录下]


