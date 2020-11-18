---
title: Obiekty rozszerzeń XSLT
ms.date: 03/30/2017
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
ms.openlocfilehash: fa9c8e0baa11d8c0e2d8099a6ddbe1c43c4d6b7f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818313"
---
# <a name="xslt-extension-objects"></a><span data-ttu-id="08090-102">Obiekty rozszerzeń XSLT</span><span class="sxs-lookup"><span data-stu-id="08090-102">XSLT Extension Objects</span></span>
<span data-ttu-id="08090-103">Obiekty rozszerzeń służą do rozszerzania funkcjonalności arkuszy stylów.</span><span class="sxs-lookup"><span data-stu-id="08090-103">Extension objects are used to extend the functionality of style sheets.</span></span> <span data-ttu-id="08090-104">Obiekty rozszerzeń są obsługiwane przez <xref:System.Xml.Xsl.XsltArgumentList> klasę.</span><span class="sxs-lookup"><span data-stu-id="08090-104">Extension objects are maintained by the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span>  
  
 <span data-ttu-id="08090-105">Poniżej przedstawiono zalety użycia obiektu rozszerzenia zamiast skryptu osadzonego:</span><span class="sxs-lookup"><span data-stu-id="08090-105">The following are advantages to using an extension object rather than embedded script:</span></span>  
  
- <span data-ttu-id="08090-106">Zapewnia lepszą hermetyzację i ponowne użycie klas.</span><span class="sxs-lookup"><span data-stu-id="08090-106">Provides better encapsulation and reuse of classes.</span></span>  
  
- <span data-ttu-id="08090-107">Zezwala na mniejsze i łatwiejsze w obsłudze arkusze stylów.</span><span class="sxs-lookup"><span data-stu-id="08090-107">Allows style sheets to be smaller and more maintainable.</span></span>  
  
 <span data-ttu-id="08090-108">Obiekty rozszerzeń XSLT są dodawane do <xref:System.Xml.Xsl.XsltArgumentList> obiektu za pomocą <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="08090-108">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> object using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="08090-109">Kwalifikowana nazwa i identyfikator URI przestrzeni nazw są skojarzone z obiektem rozszerzenia w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="08090-109">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08090-110">Zestaw uprawnień FullTrust jest wymagany do wywołania <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="08090-110">The FullTrust permission set is required to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="08090-111">Aby uzyskać więcej informacji, zobacz [zabezpieczenia dostępu kodu](../../../framework/misc/code-access-security.md) i [nazwane zestawy uprawnień](/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="08090-111">For more information, see [Code Access Security](../../../framework/misc/code-access-security.md) and [Named Permission Sets](/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).</span></span>  
  
 <span data-ttu-id="08090-112">Typy danych zwracane z obiektów rozszerzeń to jeden z czterech podstawowych typów danych XPath,,, `number` `string` `Boolean` i `node set` .</span><span class="sxs-lookup"><span data-stu-id="08090-112">The data types returned from extension objects are one of the four basic XPath data types of `number`, `string`, `Boolean`, and `node set`.</span></span>  
  
 <span data-ttu-id="08090-113">Każda metoda, która jest zdefiniowana za pomocą `params` słowa kluczowego, umożliwiająca nieokreśloną liczbę parametrów do przesłania, nie jest obecnie obsługiwana przez <xref:System.Xml.Xsl.XslCompiledTransform> klasę.</span><span class="sxs-lookup"><span data-stu-id="08090-113">Any method that is defined with the `params` keyword, which allows an unspecified number of parameters to be passed, is not currently supported by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="08090-114">Arkusze stylów XSLT używające dowolnej metody zdefiniowanej za pomocą `params` słowa kluczowego nie będą działały prawidłowo.</span><span class="sxs-lookup"><span data-stu-id="08090-114">XSLT style sheets that utilize any method defined with the `params` keyword will not work correctly.</span></span> <span data-ttu-id="08090-115">Aby uzyskać szczegółowe informacje, zobacz [params](../../../csharp/language-reference/keywords/params.md).</span><span class="sxs-lookup"><span data-stu-id="08090-115">For details, see [params](../../../csharp/language-reference/keywords/params.md).</span></span>  
  
### <a name="to-use-an-xslt-extension-object"></a><span data-ttu-id="08090-116">Aby użyć obiektu rozszerzenia XSLT</span><span class="sxs-lookup"><span data-stu-id="08090-116">To use an XSLT extension object</span></span>  
  
1. <span data-ttu-id="08090-117">Utwórz <xref:System.Xml.Xsl.XsltArgumentList> obiekt i Dodaj obiekt rozszerzenia za pomocą <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="08090-117">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span>  
  
2. <span data-ttu-id="08090-118">Wywołaj obiekt rozszerzenia z arkusza stylów.</span><span class="sxs-lookup"><span data-stu-id="08090-118">Call the extension object from the style sheet.</span></span>  
  
3. <span data-ttu-id="08090-119">Przekaż <xref:System.Xml.Xsl.XsltArgumentList> obiekt do <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="08090-119">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08090-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="08090-120">See also</span></span>

- [<span data-ttu-id="08090-121">Przekształcenia XSLT</span><span class="sxs-lookup"><span data-stu-id="08090-121">XSLT Transformations</span></span>](xslt-transformations.md)
- [<span data-ttu-id="08090-122">Zagadnienia dotyczące bezpieczeństwa danych XSLT</span><span class="sxs-lookup"><span data-stu-id="08090-122">XSLT Security Considerations</span></span>](xslt-security-considerations.md)
