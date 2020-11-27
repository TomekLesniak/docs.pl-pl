---
title: Obsługa błędów w działaniach asynchronicznych
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: 2c214ce1d0f435cda79deb6976ca9196a5d7aee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280263"
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="6efdc-102">Obsługa błędów w działaniach asynchronicznych</span><span class="sxs-lookup"><span data-stu-id="6efdc-102">Error handling in asynchronous activities</span></span>

<span data-ttu-id="6efdc-103">Obsługa błędów w programie <xref:System.Activities.AsyncCodeActivity> obejmuje kierowanie błędów za pomocą systemu wywołania zwrotnego działania.</span><span class="sxs-lookup"><span data-stu-id="6efdc-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="6efdc-104">W tym temacie opisano sposób uzyskiwania błędu zgłoszonego w operacji asynchronicznej z powrotem do hosta przy użyciu przykładu działania SendMail.</span><span class="sxs-lookup"><span data-stu-id="6efdc-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="6efdc-105">Zwracanie błędu zgłoszonego w asynchronicznym działaniu z powrotem do hosta</span><span class="sxs-lookup"><span data-stu-id="6efdc-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  

 <span data-ttu-id="6efdc-106">Kierowanie błędu w operacji asynchronicznej z powrotem do hosta w przykładowym działaniu SendMail obejmuje następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="6efdc-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
- <span data-ttu-id="6efdc-107">Dodaj właściwość wyjątku do `SendMailAsyncResult` klasy.</span><span class="sxs-lookup"><span data-stu-id="6efdc-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
- <span data-ttu-id="6efdc-108">Skopiuj zgłoszony błąd do tej właściwości w `SendCompleted` obsłudze zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="6efdc-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
- <span data-ttu-id="6efdc-109">Zgłoś wyjątek w `EndExecute` obsłudze zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="6efdc-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="6efdc-110">Otrzymany kod jest następujący:</span><span class="sxs-lookup"><span data-stu-id="6efdc-110">The resulting code is as follows.</span></span>  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;
        }  
    }  
```
