finagle-codereading
===================

Client Builder
==============

source code
-----------
[client builder src]

code reading
------------
在ClientBuilder单例中，定义了几个类型,目的是判断builder是否完整，如果缺少codec或者cluster信息，编译会出错:
<pre><code>
  type Complete[Req, Rep] =
    ClientBuilder[Req, Rep, ClientConfig.Yes, ClientConfig.Yes, ClientConfig.Yes]
  type NoCluster[Req, Rep] =
    ClientBuilder[Req, Rep, Nothing, ClientConfig.Yes, ClientConfig.Yes]
  type NoCodec =
    ClientBuilder[_, _, ClientConfig.Yes, Nothing, ClientConfig.Yes]
</code></pre>






[client builde src]:https://github.com/twitter/finagle/blob/master/finagle-core/src/main/scala/com/twitter/finagle/builder/ClientBuilder.scala
