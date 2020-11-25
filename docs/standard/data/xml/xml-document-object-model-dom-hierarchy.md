---
title: Hierarchia modelu DOM (XML Document Object Model)
ms.date: 03/30/2017
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 24ef51a18392fe3034e64bd585d879941fca4b95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718361"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="fce83-102">Hierarchia modelu DOM (XML Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="fce83-102">XML Document Object Model (DOM) Hierarchy</span></span>

<span data-ttu-id="fce83-103">Na poniższej ilustracji przedstawiono hierarchię klas dla Document Object Model XML (DOM), z nazwą organizacja World Wide Web Consortium (W3C) w nawiasie wraz z nazwą klasy, w której ma zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="fce83-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="fce83-104">![Hierarchia&#41; Document Object Model XML &#40;DOM](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="fce83-104">![XML Document Object Model &#40;DOM&#41; hierarchy](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="fce83-105">Hierarchia XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="fce83-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="fce83-106">Następujące klasy nie dziedziczą z **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="fce83-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="fce83-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="fce83-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="fce83-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="fce83-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="fce83-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="fce83-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="fce83-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="fce83-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="fce83-111">Klasa **XmlImplementation** służy do tworzenia dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="fce83-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="fce83-112">Aby uzyskać więcej informacji, zobacz [Tworzenie dokumentów XML](xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="fce83-112">For more information, see [XML Document Creation](xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="fce83-113">Klasa **XmlNamedNodeMap** obsługuje nieuporządkowany zestaw węzłów.</span><span class="sxs-lookup"><span data-stu-id="fce83-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="fce83-114">Aby uzyskać więcej informacji, zobacz [nieuporządkowane pobieranie węzłów według nazwy lub indeksu](unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="fce83-114">For more information, see [Unordered Node Retrieval by Name or Index](unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="fce83-115">Klasa **XmlNodeList** obsługuje uporządkowaną listę węzłów.</span><span class="sxs-lookup"><span data-stu-id="fce83-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="fce83-116">Aby uzyskać więcej informacji, zobacz [uporządkowane pobieranie węzłów według indeksu](ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="fce83-116">For more information, see [Ordered Node Retrieval by Index](ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="fce83-117">Klasa **XmlNodeChangedEventArgs** obsługuje programy obsługi zdarzeń zarejestrowane w **dokumencie XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="fce83-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="fce83-118">Aby uzyskać więcej informacji, zobacz [Obsługa zdarzeń w dokumencie XML przy użyciu XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="fce83-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="fce83-119">Klasa **XmlLinkedNode** dziedziczy z klasy **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="fce83-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="fce83-120">Celem jest przesłonięcie dwóch metod z klasy **XmlNode**: metod **PreviousSibling** i **NextSibling** .</span><span class="sxs-lookup"><span data-stu-id="fce83-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="fce83-121">Te zastąpione metody są następnie dziedziczone i używane przez **XmlCharacterData**, **xmldeklaracji**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** i **XmlProcessingInstruction**, które są klasami, które mają poprzednie i następne elementy równorzędne.</span><span class="sxs-lookup"><span data-stu-id="fce83-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce83-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fce83-122">See also</span></span>

- [<span data-ttu-id="fce83-123">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="fce83-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
