
2024/4/9
//Callback & listener的区分

Callback

例如：
（1）Server:class A {registerCallback1 ， registerCallback2}

Client:class B
Client:class C

aidl_interface iD

（2）callback大致流程
B --> IBinder(iD).registerCallback1 --> A.registerCallback1(*funcB) --> A.callback1 = funcB;
C --> IBinder(iD).registerCallback2 --> A.registerCallback2(*funcC) --> A.callback2 = funcC;

在A中调用callback1和callback2。


（3）listener流程

B.addListener(Blistener) -> IBinder(iD).addListener -> A.addListener 将Blistener加入listener list里面
C.addListener(Clistener) -> IBinder(iD).addListener -> A.addListener 将Clistener加入listener list里面
在A中，有事件发生时，例如 状态or输入 变化，触发listner change , 通知listner list里面的所有注册的listener。


**listener 事件驱动，事件源为 server，对应多个 Client。**

**Callback：server暴露一个接口出来registerCallback， Client 调用此接口,传入一个函数指针，Server使用Client的服务指针，并在某个地方进行调用**
