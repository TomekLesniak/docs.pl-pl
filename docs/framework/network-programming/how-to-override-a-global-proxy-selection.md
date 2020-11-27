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
# <a name="how-to-override-a-global-proxy-selection"></a>Instrukcje: zastępowanie wyboru globalnego serwera proxy

W tym przykładzie wysłano **żądanie** sieci webdo `www.contoso.com` , które zastąpi globalny wybór serwera proxy serwerem proxy o nazwie `alternateproxy` na porcie 80.  
  
## <a name="example"></a>Przykład  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Ten przykład wymaga:  
  
- [ `using` Dyrektywa](../../csharp/language-reference/keywords/using-directive.md) dla przestrzeni nazw **System.NET** .  
  
## <a name="see-also"></a>Zobacz też

- [Korzystanie z protokołów aplikacji](using-application-protocols.md)
- [Dostęp do Internetu za pośrednictwem serwera proxy](accessing-the-internet-through-a-proxy.md)
