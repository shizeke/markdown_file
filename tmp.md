
2024/4/9
//Callback & listener的区分

Callback
eg:
Server:class A {registerCallback1 ， registerCallback2}

Client:class B
Client:class C


aidl_interface iD


B --> IBinder(iD).registerCallback1 --> A.registerCallback1(*funcB) --> A.callback1 = funcB;

C --> IBinder(iD).registerCallback2 --> A.registerCallback2(*funcC) --> A.callback2 = funcC;


不能用Callback，需要用listener。


**listener 事件驱动，事件源为 server，对应多个 Client。**

**Callback：server暴露一个接口出来registerCallback， Client 调用此接口,传入一个函数指针，Server使用Client的服务指针，并在某个地方进行调用**
