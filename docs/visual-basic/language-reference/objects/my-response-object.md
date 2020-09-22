---
title: My.Response — Obiekt
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 53e8012e762c46e6efbd8e9d2191aa62d58aa42b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870044"
---
# <a name="myresponse-object"></a>My.Response — Obiekt

Pobiera <xref:System.Web.HttpResponse> obiekt skojarzony z <xref:System.Web.UI.Page> . Ten obiekt umożliwia wysyłanie danych odpowiedzi HTTP do klienta programu i zawiera informacje o tej odpowiedzi.  
  
## <a name="remarks"></a>Uwagi  

 `My.Response`Obiekt zawiera bieżący <xref:System.Web.HttpResponse> obiekt skojarzony ze stroną.  
  
 `My.Response`Obiekt jest dostępny tylko dla aplikacji ASP.NET.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pobiera kolekcję nagłówka z `My.Request` obiektu i używa `My.Response` obiektu do zapisania go na stronie ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Web.HttpResponse>
- [My.Request — Obiekt](my-request-object.md)
