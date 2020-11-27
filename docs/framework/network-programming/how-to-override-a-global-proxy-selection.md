---
title: 'Instrukcje: zastępowanie wyboru globalnego serwera proxy'
description: Postępuj zgodnie z tym przykładem, aby zastąpić globalne Wybieranie serwera proxy przez wysłanie żądania webżądanie do adresu URL, które zastępuje wybór z serwerem proxy.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 8931cdc471b957447277c333ba482a0cec0e6aa5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265742"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="13684-103">Instrukcje: zastępowanie wyboru globalnego serwera proxy</span><span class="sxs-lookup"><span data-stu-id="13684-103">How to: Override a Global Proxy Selection</span></span>

<span data-ttu-id="13684-104">W tym przykładzie wysłano **żądanie** sieci webdo `www.contoso.com` , które zastąpi globalny wybór serwera proxy serwerem proxy o nazwie `alternateproxy` na porcie 80.</span><span class="sxs-lookup"><span data-stu-id="13684-104">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13684-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="13684-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13684-106">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="13684-106">Compiling the Code</span></span>  

 <span data-ttu-id="13684-107">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="13684-107">This example requires:</span></span>  
  
- <span data-ttu-id="13684-108">[ `using` Dyrektywa](../../csharp/language-reference/keywords/using-directive.md) dla przestrzeni nazw **System.NET** .</span><span class="sxs-lookup"><span data-stu-id="13684-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13684-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="13684-109">See also</span></span>

- [<span data-ttu-id="13684-110">Korzystanie z protokołów aplikacji</span><span class="sxs-lookup"><span data-stu-id="13684-110">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="13684-111">Dostęp do Internetu za pośrednictwem serwera proxy</span><span class="sxs-lookup"><span data-stu-id="13684-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
