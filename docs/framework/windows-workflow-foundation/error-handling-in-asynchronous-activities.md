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
# <a name="error-handling-in-asynchronous-activities"></a>Obsługa błędów w działaniach asynchronicznych

Obsługa błędów w programie <xref:System.Activities.AsyncCodeActivity> obejmuje kierowanie błędów za pomocą systemu wywołania zwrotnego działania. W tym temacie opisano sposób uzyskiwania błędu zgłoszonego w operacji asynchronicznej z powrotem do hosta przy użyciu przykładu działania SendMail.  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a>Zwracanie błędu zgłoszonego w asynchronicznym działaniu z powrotem do hosta  

 Kierowanie błędu w operacji asynchronicznej z powrotem do hosta w przykładowym działaniu SendMail obejmuje następujące kroki:  
  
- Dodaj właściwość wyjątku do `SendMailAsyncResult` klasy.  
  
- Skopiuj zgłoszony błąd do tej właściwości w `SendCompleted` obsłudze zdarzeń.  
  
- Zgłoś wyjątek w `EndExecute` obsłudze zdarzeń.  
  
 Otrzymany kod jest następujący:  
  
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
