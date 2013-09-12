HXRoute
=======

hxroute是一个URL路由库，类似Django的URL配置，通过输入的URL匹配出执行的方法。

URL路由是WEB MVC中非常重要的一个环节，hxroute并不打算做一个大而全的web框架，
就像他的名字一样，非常灵活只负责找出URL映射的方法，并不做其他事情。

你可以轻易的把他集成到你的web项目中，选择自己喜欢的映射方式。

    Route
        .addPackage("user", alias="member");

    Route
        .namespace("user.controllers")
        .add("/", "User")
        .add("/register/", "Register")
        .add("/:id/", "UserProfile");

    var mapper = route.match("/1");
    Assert.areEqual("1", mapper.parameters[0]);


自定义URL分析器
--------------

    Route.setURLParser(parser);

自定义派发器
-----------

    Route.setDispatcher(dispatcher);