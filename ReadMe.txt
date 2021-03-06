C#并发编程经典实例阅读笔记说明：
误解：
实际上多线程只是并发编程的一种形式，还包括了异步编程、并行编程、TPL数据流、响应式编程。
简介：
并发：同时做多件事
多线程：并发的一种形式，采用了多个线程来执行程序
并行处理：把正在执行的大量任务分割成小块，分配给多个同时运行的线程
异步编程：并发的一种形式，采用future模式或者回调(Callback)机制，以避免产生不必要的线程
响应式：一种声明式的编程模式，程序在该模式中对事件做出相应

注意：
在并发编程中，Task类有两个作用，作为并行任务，或者作为异步任务。并行任务可以使用阻塞的成员函数，例如 Task.Result、Task.Wait、Task.WaitAll、Task.WaitAny。并行任务通常也使用 AttachedToParent 来建立父子任务之间的“父/子”关系。并行任务的创建需要用Task.Run或者Task.Factory.StratNew。
相反，异步任务应该避免使用阻塞的函数调用，而应该使用 await、Task.WhenAlll、Task.WhenAny。异步任务不使用AccathcedToParent,但可以通过 await 另一个任务，建立一种隐式的 父子 关系。