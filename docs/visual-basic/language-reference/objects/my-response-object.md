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
# <a name="myresponse-object"></a><span data-ttu-id="d0b5c-102">My.Response — Obiekt</span><span class="sxs-lookup"><span data-stu-id="d0b5c-102">My.Response Object</span></span>

<span data-ttu-id="d0b5c-103">Pobiera <xref:System.Web.HttpResponse> obiekt skojarzony z <xref:System.Web.UI.Page> .</span><span class="sxs-lookup"><span data-stu-id="d0b5c-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="d0b5c-104">Ten obiekt umożliwia wysyłanie danych odpowiedzi HTTP do klienta programu i zawiera informacje o tej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="d0b5c-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0b5c-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d0b5c-105">Remarks</span></span>  

 <span data-ttu-id="d0b5c-106">`My.Response`Obiekt zawiera bieżący <xref:System.Web.HttpResponse> obiekt skojarzony ze stroną.</span><span class="sxs-lookup"><span data-stu-id="d0b5c-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="d0b5c-107">`My.Response`Obiekt jest dostępny tylko dla aplikacji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d0b5c-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0b5c-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="d0b5c-108">Example</span></span>  

 <span data-ttu-id="d0b5c-109">Poniższy przykład pobiera kolekcję nagłówka z `My.Request` obiektu i używa `My.Response` obiektu do zapisania go na stronie ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d0b5c-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d0b5c-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d0b5c-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="d0b5c-111">My.Request — Obiekt</span><span class="sxs-lookup"><span data-stu-id="d0b5c-111">My.Request Object</span></span>](my-request-object.md)
