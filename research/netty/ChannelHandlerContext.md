###  ChannelHandlerContext
ChannelHandler上下文接口声明，继承ChannelInboundInvoker, ChannelOutboundInvoker，用于在Channel中有事件或者消息发生时触发inbound或者outbound的事件或消息传递。

#### AbstractChannelHandlerContext
Skeleton implement of ChannelHandlerContext.
+ __AbstractChannelHandlerContext__ prev & next 链表前后指针
+ __HANDLER_STATE_UPDATER__ 关联的ChannelHanddler状态更新器（四种状态：INIT, ADD_PENDING, ADD_COMPLETE, REMOVE_COMPLETE)
+ __inbound & outbound__ 事件或者消息流动方向
+ __DefaultChannelPipeline__ pipeline 关联的ChannelPipeline
+ __name__
+ __boolean ordered__
+ __EventExecutor executor__ 如果在从执行器中执行，设置为当前的执行器，否则置空

AbstractChannelHandlerContext实现了ChannelInboundInvoker与ChannelOutboundInvoker定义的所有接口，其中InboundInvoker主要定义了对Channel状态变化的处理接口fireChannelXXX, OutBoundInvoker主要定义了网络操作接口，包括connect，bind，read，write等。
