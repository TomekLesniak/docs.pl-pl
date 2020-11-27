---
title: 'Instrukcje: dostęp do właściwości specyficznych dla protokołu HTTP'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: ea709bba17d4e2f00b760c8713f9e8100496f0bf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250518"
---
# <a name="how-to-access-http-specific-properties"></a>Instrukcje: dostęp do właściwości specyficznych dla protokołu HTTP

Ten przykład pokazuje, jak wyłączyć zachowanie **Keep-Alive** protokołu HTTP i uzyskać numer wersji protokołu z serwera sieci Web.  
  
## <a name="example"></a>Przykład  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Ten przykład wymaga:  
  
- Odwołania do przestrzeni nazw **System.NET** .  
  
## <a name="see-also"></a>Zobacz też

- [Dostęp do Internetu za pośrednictwem serwera proxy](accessing-the-internet-through-a-proxy.md)
- [Korzystanie z protokołów aplikacji](using-application-protocols.md)
- [HTTP](http.md)
