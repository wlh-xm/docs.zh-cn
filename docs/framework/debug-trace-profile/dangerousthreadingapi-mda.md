---
title: dangerousThreadingAPI MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
caps.latest.revision: 10
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fd0d8b8a4a96e1e92aa8cf58ee49adf7b51857ab
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="dangerousthreadingapi-mda"></a><span data-ttu-id="dc696-102">dangerousThreadingAPI MDA</span><span class="sxs-lookup"><span data-stu-id="dc696-102">dangerousThreadingAPI MDA</span></span>
<span data-ttu-id="dc696-103">如果在当前线程以外的线程上调用 <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> 方法，将激活 `dangerousThreadingAPI` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="dc696-103">The `dangerousThreadingAPI` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> method is called on a thread other than the current thread.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="dc696-104">症状</span><span class="sxs-lookup"><span data-stu-id="dc696-104">Symptoms</span></span>  
 <span data-ttu-id="dc696-105">应用程序无响应或无限期挂起。</span><span class="sxs-lookup"><span data-stu-id="dc696-105">An application is unresponsive or hangs indefinitely.</span></span> <span data-ttu-id="dc696-106">系统数据或应用程序数据可能暂时处于不可预知状态，甚至在应用程序关闭之后也可能处于不可预知状态。</span><span class="sxs-lookup"><span data-stu-id="dc696-106">System or application data might be left in an unpredictable state temporarily or even after an application has been shut down.</span></span> <span data-ttu-id="dc696-107">某些操作未按预期完成。</span><span class="sxs-lookup"><span data-stu-id="dc696-107">Some operations are not completing as expected.</span></span>  
  
 <span data-ttu-id="dc696-108">由于问题固有的随机性，因此问题的具体表现可能有极大差异。</span><span class="sxs-lookup"><span data-stu-id="dc696-108">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="dc696-109">原因</span><span class="sxs-lookup"><span data-stu-id="dc696-109">Cause</span></span>  
 <span data-ttu-id="dc696-110">一个线程使用 <xref:System.Threading.Thread.Suspend%2A> 方法将另一线程异步挂起。</span><span class="sxs-lookup"><span data-stu-id="dc696-110">A thread is asynchronously suspended by another thread using the <xref:System.Threading.Thread.Suspend%2A> method.</span></span> <span data-ttu-id="dc696-111">无法确定何时挂起另一个可能正在操作的线程才安全。</span><span class="sxs-lookup"><span data-stu-id="dc696-111">There is no way to determine when it is safe to suspend another thread which might be in the middle of an operation.</span></span> <span data-ttu-id="dc696-112">挂起线程会导致数据损坏或不变体中断。</span><span class="sxs-lookup"><span data-stu-id="dc696-112">Suspending the thread can result in the corruption of data or the breaking of invariants.</span></span> <span data-ttu-id="dc696-113">如果一个线程处于挂起状态且从未使用 <xref:System.Threading.Thread.Resume%2A> 方法恢复，则应用程序可能会无限期挂起且应用程序数据可能会遭到损坏。</span><span class="sxs-lookup"><span data-stu-id="dc696-113">Should a thread be placed into a suspended state and never resumed using the <xref:System.Threading.Thread.Resume%2A> method, the application can hang indefinitely and possibly damage application data.</span></span> <span data-ttu-id="dc696-114">这些方法已被标记为已过时。</span><span class="sxs-lookup"><span data-stu-id="dc696-114">These methods have been marked as obsolete.</span></span>  
  
 <span data-ttu-id="dc696-115">如果由目标线程保留同步基元，则挂起期间仍然保留这些同步基元。</span><span class="sxs-lookup"><span data-stu-id="dc696-115">If synchronization primitives are held by the target thread, they remain held during suspension.</span></span> <span data-ttu-id="dc696-116">如果另一线程（例如执行 <xref:System.Threading.Thread.Suspend%2A> 的线程）尝试获取对该基元的锁定，则这可能会导致死锁。</span><span class="sxs-lookup"><span data-stu-id="dc696-116">This can lead to deadlocks should another thread, for example the thread performing the <xref:System.Threading.Thread.Suspend%2A>, attempt to acquire a lock on the primitive.</span></span> <span data-ttu-id="dc696-117">在此情况下，该问题将自身表示为死锁。</span><span class="sxs-lookup"><span data-stu-id="dc696-117">In this situation, the problem manifests itself as a deadlock.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="dc696-118">解决方法</span><span class="sxs-lookup"><span data-stu-id="dc696-118">Resolution</span></span>  
 <span data-ttu-id="dc696-119">避免需使用 <xref:System.Threading.Thread.Suspend%2A> 和 <xref:System.Threading.Thread.Resume%2A> 的设计。</span><span class="sxs-lookup"><span data-stu-id="dc696-119">Avoid designs that require the use of <xref:System.Threading.Thread.Suspend%2A> and <xref:System.Threading.Thread.Resume%2A>.</span></span> <span data-ttu-id="dc696-120">对于线程之间的协作，请使用 <xref:System.Threading.Monitor>、<xref:System.Threading.ReaderWriterLock>、<xref:System.Threading.Mutex> 或 C# `lock` 语句等同步基元。</span><span class="sxs-lookup"><span data-stu-id="dc696-120">For cooperation between threads, use synchronization primitives such as <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex>, or the C# `lock` statement.</span></span> <span data-ttu-id="dc696-121">如果必须使用这些方法，则请缩短时间范围并最大限度地减少线程处于挂起状态时执行的代码量。</span><span class="sxs-lookup"><span data-stu-id="dc696-121">If you must use these methods, reduce the window of time and minimize the amount of code that executes while the thread is in a suspended state.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="dc696-122">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="dc696-122">Effect on the Runtime</span></span>  
 <span data-ttu-id="dc696-123">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="dc696-123">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="dc696-124">它只报告有关危险线程处理操作的数据。</span><span class="sxs-lookup"><span data-stu-id="dc696-124">It only reports data about dangerous threading operations.</span></span>  
  
## <a name="output"></a><span data-ttu-id="dc696-125">输出</span><span class="sxs-lookup"><span data-stu-id="dc696-125">Output</span></span>  
 <span data-ttu-id="dc696-126">MDA 识别导致其激活的危险线程处理方法。</span><span class="sxs-lookup"><span data-stu-id="dc696-126">The MDA identifies the dangerous threading method that caused it to be activated.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="dc696-127">配置</span><span class="sxs-lookup"><span data-stu-id="dc696-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="dc696-128">示例</span><span class="sxs-lookup"><span data-stu-id="dc696-128">Example</span></span>  
 <span data-ttu-id="dc696-129">以下代码示例演示对造成 `dangerousThreadingAPI` 激活的 <xref:System.Threading.Thread.Suspend%2A> 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="dc696-129">The following code example demonstrates a call to the <xref:System.Threading.Thread.Suspend%2A> method that causes the activation of the `dangerousThreadingAPI`.</span></span>  
  
```  
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc696-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc696-130">See Also</span></span>  
 <span data-ttu-id="dc696-131"><xref:System.Threading.Thread></span><span class="sxs-lookup"><span data-stu-id="dc696-131"><xref:System.Threading.Thread></span></span>   
 <span data-ttu-id="dc696-132">[使用托管调试助手诊断错误](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span><span class="sxs-lookup"><span data-stu-id="dc696-132">[Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md) </span></span>  
 [<span data-ttu-id="dc696-133">lock 语句</span><span class="sxs-lookup"><span data-stu-id="dc696-133">lock Statement</span></span>](~/docs/csharp/language-reference/keywords/lock-statement.md)
