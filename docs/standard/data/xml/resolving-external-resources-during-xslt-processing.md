---
title: Rozpoznawanie zewnętrznych zasobów podczas przetwarzania XSLT
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
ms.openlocfilehash: 5d50711eda266cecdb817c778f04aa845fa4c342
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686647"
---
# <a name="resolving-external-resources-during-xslt-processing"></a><span data-ttu-id="3d54c-102">Rozpoznawanie zewnętrznych zasobów podczas przetwarzania XSLT</span><span class="sxs-lookup"><span data-stu-id="3d54c-102">Resolving External Resources During XSLT Processing</span></span>

<span data-ttu-id="3d54c-103">Podczas transformacji XSLT występuje kilka razy, gdy konieczne jest rozwiązanie zasobów zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="3d54c-103">There are several times during an XSLT transformation when you may need to resolve external resources.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="3d54c-104">Korzystanie z klasy XmlResolver</span><span class="sxs-lookup"><span data-stu-id="3d54c-104">Using the XmlResolver Class</span></span>  

 <span data-ttu-id="3d54c-105"><xref:System.Xml.XmlResolver>Klasa jest używana do rozpoznawania zasobów zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="3d54c-105">The <xref:System.Xml.XmlResolver> class is used to resolve external resources.</span></span> <span data-ttu-id="3d54c-106">W poniższej tabeli opisano, kiedy zostanie <xref:System.Xml.XmlResolver> ona uwzględniona podczas przetwarzania XSLT.</span><span class="sxs-lookup"><span data-stu-id="3d54c-106">The following table describes when the <xref:System.Xml.XmlResolver> becomes involved during XSLT processing.</span></span>  
  
|<span data-ttu-id="3d54c-107">Zadanie XSLT</span><span class="sxs-lookup"><span data-stu-id="3d54c-107">XSLT task</span></span>|<span data-ttu-id="3d54c-108">Do czego służy element XmlResolver</span><span class="sxs-lookup"><span data-stu-id="3d54c-108">What the XmlResolver is used for</span></span>|  
|---------------|--------------------------------------|  
|<span data-ttu-id="3d54c-109">Kompiluj arkusz stylów.</span><span class="sxs-lookup"><span data-stu-id="3d54c-109">Compile the style sheet.</span></span>|<span data-ttu-id="3d54c-110">Rozpoznanie identyfikatora URI arkusza stylów.</span><span class="sxs-lookup"><span data-stu-id="3d54c-110">Resolve the URI of the style sheet.</span></span><br /><br /> <span data-ttu-id="3d54c-111">lub</span><span class="sxs-lookup"><span data-stu-id="3d54c-111">-and-</span></span><br /><br /> <span data-ttu-id="3d54c-112">Rozpoznaj odwołania do identyfikatorów URI w dowolnych `xsl:import` lub `xsl:include` elementach.</span><span class="sxs-lookup"><span data-stu-id="3d54c-112">Resolve URI references in any `xsl:import` or `xsl:include` elements.</span></span>|  
|<span data-ttu-id="3d54c-113">Wykonaj arkusz stylów.</span><span class="sxs-lookup"><span data-stu-id="3d54c-113">Execute the style sheet.</span></span>|<span data-ttu-id="3d54c-114">Rozpoznanie identyfikatora URI dokumentu kontekstowego.</span><span class="sxs-lookup"><span data-stu-id="3d54c-114">Resolve the URI of the context document.</span></span><br /><br /> <span data-ttu-id="3d54c-115">lub</span><span class="sxs-lookup"><span data-stu-id="3d54c-115">-and-</span></span><br /><br /> <span data-ttu-id="3d54c-116">Rozpoznawanie odwołań do identyfikatorów URI w dowolnych `document()` funkcjach XSLT.</span><span class="sxs-lookup"><span data-stu-id="3d54c-116">Resolve URI references in any XSLT `document()` functions.</span></span>|  
  
 <span data-ttu-id="3d54c-117"><xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>Metody i <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> obejmują przeciążenia przyjmujące <xref:System.Xml.XmlResolver> obiekt jako jeden z argumentów.</span><span class="sxs-lookup"><span data-stu-id="3d54c-117">The <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> and <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> methods include overloads that take an <xref:System.Xml.XmlResolver> object as one of its arguments.</span></span> <span data-ttu-id="3d54c-118">Jeśli <xref:System.Xml.XmlResolver> nie jest określony, <xref:System.Xml.XmlUrlResolver> zostanie użyta wartość domyślna bez poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="3d54c-118">If an <xref:System.Xml.XmlResolver> is not specified, a default <xref:System.Xml.XmlUrlResolver> with no credentials is used.</span></span>  
  
 <span data-ttu-id="3d54c-119">Na poniższej liście opisano, kiedy warto określić <xref:System.Xml.XmlResolver> obiekt:</span><span class="sxs-lookup"><span data-stu-id="3d54c-119">The following list describes when you may want to specify an <xref:System.Xml.XmlResolver> object:</span></span>  
  
- <span data-ttu-id="3d54c-120">Jeśli proces XSLT musi uzyskać dostęp do zasobu sieciowego, który wymaga uwierzytelnienia, możesz użyć <xref:System.Xml.XmlResolver> z niezbędnymi poświadczeniami.</span><span class="sxs-lookup"><span data-stu-id="3d54c-120">If the XSLT process needs to access a network resource that requires authentication, you can use an <xref:System.Xml.XmlResolver> with the necessary credentials.</span></span>  
  
- <span data-ttu-id="3d54c-121">Jeśli chcesz ograniczyć zasoby, do których proces XSLT może uzyskać dostęp, możesz użyć <xref:System.Xml.XmlSecureResolver> z prawidłowym zestawem uprawnień.</span><span class="sxs-lookup"><span data-stu-id="3d54c-121">If you want to restrict the resources that the XSLT process can access, you can use an <xref:System.Xml.XmlSecureResolver> with the correct permission set.</span></span> <span data-ttu-id="3d54c-122">Użyj <xref:System.Xml.XmlSecureResolver> klasy, jeśli konieczne jest otwarcie zasobu, którego nie kontrolujesz lub który nie jest zaufany.</span><span class="sxs-lookup"><span data-stu-id="3d54c-122">Use the <xref:System.Xml.XmlSecureResolver> class if you need to open a resource that you do not control, or that is untrusted.</span></span>  
  
- <span data-ttu-id="3d54c-123">Jeśli chcesz dostosować zachowanie, możesz zaimplementować własną <xref:System.Xml.XmlResolver> klasę i używać jej do rozwiązywania zasobów.</span><span class="sxs-lookup"><span data-stu-id="3d54c-123">If you want to customize behavior, you can implement your own <xref:System.Xml.XmlResolver> class and use it to resolve resources.</span></span>  
  
- <span data-ttu-id="3d54c-124">Jeśli chcesz się upewnić, że nie ma dostępu do zasobów zewnętrznych, możesz określić `null` dla tego <xref:System.Xml.XmlResolver> argumentu.</span><span class="sxs-lookup"><span data-stu-id="3d54c-124">If you want to ensure that no external resources are accessed, you can specify `null` for the <xref:System.Xml.XmlResolver> argument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d54c-125">Przykład</span><span class="sxs-lookup"><span data-stu-id="3d54c-125">Example</span></span>  

 <span data-ttu-id="3d54c-126">Poniższy przykład kompiluje arkusz stylów, który jest przechowywany w zasobów sieciowych.</span><span class="sxs-lookup"><span data-stu-id="3d54c-126">The following example compiles a style sheet that is stored on a network resource.</span></span> <span data-ttu-id="3d54c-127"><xref:System.Xml.XmlUrlResolver>Obiekt określa poświadczenia niezbędne do uzyskania dostępu do arkusza stylów.</span><span class="sxs-lookup"><span data-stu-id="3d54c-127">An <xref:System.Xml.XmlUrlResolver> object specifies the credentials necessary to access the style sheet.</span></span>  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="3d54c-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3d54c-128">See also</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform>
- <xref:System.Xml.Xsl.XsltSettings>
- [<span data-ttu-id="3d54c-129">Przekształcenia XSLT</span><span class="sxs-lookup"><span data-stu-id="3d54c-129">XSLT Transformations</span></span>](xslt-transformations.md)
