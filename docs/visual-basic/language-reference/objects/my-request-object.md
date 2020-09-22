---
title: My.Request — Obiekt
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: d0459506994fb69ebfaa4186ba137044b6fe9464
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870077"
---
# <a name="myrequest-object"></a>My.Request — Obiekt

Pobiera <xref:System.Web.HttpRequest> obiekt dla żądanej strony.  
  
## <a name="remarks"></a>Uwagi  

 `My.Request`Obiekt zawiera informacje o bieżącym ŻĄDANIU http.  
  
 `My.Request`Obiekt jest dostępny tylko dla aplikacji ASP.NET.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pobiera kolekcję nagłówka z `My.Request` obiektu i używa `My.Response` obiektu do zapisania go na stronie ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Web.HttpRequest>
- [My.Response — Obiekt](my-response-object.md)
