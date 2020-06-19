## netty
jdk bio，nio，aio各种使用案例，深入理解netty，结合源码以及文章分析：
1. jdk原生nio的Buffer使用
2. jdk原生的nio channel使用
3. jdk原生的nio网络编程
4. jdk原生的reactor编程模型（使用selector） 聊天室
5. 零拷贝使用案例  文件上传
6. netty 的演变模型（3中reactor使用案例   线程池的添加时机）.
7. netty的启动源码（对照之前jdk的写法分析） NioEventLoopGroup 中的成员变量分析（线程池）
8. ChannelHandlerContext和ChannelPipeLine以及Channel的关系
9. 使用netty自带的编码解码器编写一个聊天室
10. 在9的基础上加入私聊功能
11. 在10的基础上加入protobuf的反序列化，提高效率
12. netty在解码过程中的拆包，粘包（由于不知道传输过程是否会一次性传过来一个协议的数据）ByteToMessageDecoder
13. handler执行顺序，结合12  分析 入站， 出站 代码， MessageToByteEncoder
13. writeAndFlush在 channel和ChannelHandlerContext中的区别 (调换 Encoder的位置，找出区别， 最后debug到HeadContext 的flush方法）
以及执行过程（executemask的作用）  writeAndFlush 源码执行流程
14. channel最后flush的时候调用javaChannel() write 生成了一个DirectByteBuff 可以提高效率
16. EventExecutorGroup  EventExecutor
                        EventLoopGroup  EventLoop  SingleThreadEventLoop  NioEventLoop 关系

17. debug NioEventLoop的源码run (processSelectedKeys(注意finally块有一个runAllTasks方法，确保完成所有channel事件后，在从这个线程执行所有的task任务）->
processSelectedKeysPlain)，跟踪ChannelPipeline的初始read() 触发是怎么开始的

18. NioServerSocketChannel是如何被创建的以及是如何真正绑定java channel的
19. to be continue...