---
title: Hierarchia modelu DOM (XML Document Object Model)
ms.date: 03/30/2017
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 2a8bbd4f7cb3feb2a555af9862632a2fa493be32
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819256"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="60961-102">Hierarchia modelu DOM (XML Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="60961-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="60961-103">Na poniższej ilustracji przedstawiono hierarchię klas dla Document Object Model XML (DOM), z nazwą organizacja World Wide Web Consortium (W3C) w nawiasie wraz z nazwą klasy, w której ma zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="60961-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="60961-104">![Hierarchia&#41; Document Object Model XML &#40;DOM](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="60961-104">![XML Document Object Model &#40;DOM&#41; hierarchy](media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="60961-105">Hierarchia XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="60961-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="60961-106">Następujące klasy nie dziedziczą z **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="60961-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="60961-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="60961-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="60961-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="60961-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="60961-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="60961-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="60961-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="60961-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="60961-111">Klasa **XmlImplementation** służy do tworzenia dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="60961-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="60961-112">Aby uzyskać więcej informacji, zobacz [Tworzenie dokumentów XML](xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="60961-112">For more information, see [XML Document Creation](xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="60961-113">Klasa **XmlNamedNodeMap** obsługuje nieuporządkowany zestaw węzłów.</span><span class="sxs-lookup"><span data-stu-id="60961-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="60961-114">Aby uzyskać więcej informacji, zobacz [nieuporządkowane pobieranie węzłów według nazwy lub indeksu](unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="60961-114">For more information, see [Unordered Node Retrieval by Name or Index](unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="60961-115">Klasa **XmlNodeList** obsługuje uporządkowaną listę węzłów.</span><span class="sxs-lookup"><span data-stu-id="60961-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="60961-116">Aby uzyskać więcej informacji, zobacz [uporządkowane pobieranie węzłów według indeksu](ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="60961-116">For more information, see [Ordered Node Retrieval by Index](ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="60961-117">Klasa **XmlNodeChangedEventArgs** obsługuje programy obsługi zdarzeń zarejestrowane w **dokumencie XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="60961-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="60961-118">Aby uzyskać więcej informacji, zobacz [Obsługa zdarzeń w dokumencie XML przy użyciu XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="60961-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="60961-119">Klasa **XmlLinkedNode** dziedziczy z klasy **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="60961-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="60961-120">Celem jest przesłonięcie dwóch metod z klasy **XmlNode**: metod **PreviousSibling** i **NextSibling** .</span><span class="sxs-lookup"><span data-stu-id="60961-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="60961-121">Te zastąpione metody są następnie dziedziczone i używane przez **XmlCharacterData**, **xmldeklaracji**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** i **XmlProcessingInstruction**, które są klasami, które mają poprzednie i następne elementy równorzędne.</span><span class="sxs-lookup"><span data-stu-id="60961-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60961-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="60961-122">See also</span></span>

- [<span data-ttu-id="60961-123">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="60961-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
