---
title: 'Instrukcje: rejestrowanie protokołu niestandardowego przy użyciu elementu WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 86ad862dbff9f4a982eec27a6806bcbb6c16f3ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255809"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Instrukcje: rejestrowanie protokołu niestandardowego przy użyciu elementu WebRequest

Ten przykład pokazuje, jak zarejestrować klasę specyficzną dla protokołu, która została zdefiniowana w innym miejscu. W tym przykładzie `CustomWebRequestCreator` jest obiektem implementowanym przez użytkownika, który implementuje metodę **Create** , która zwraca `CustomWebRequest` obiekt. W przykładzie kodu założono, że Zapisano `CustomWebRequest` kod implementujący niestandardowy protokół.  
  
## <a name="example"></a>Przykład  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Ten przykład wymaga:  
  
 Odwołania do <xref:System.Net> przestrzeni nazw.  
  
## <a name="see-also"></a>Zobacz też

- [Programowanie protokołów podłączanych](programming-pluggable-protocols.md)
