---
title: Prawidłowa zawartość obiektów XElement i XDocument-LINQ to XML
description: Konstruktory XElement i XDocumenty akceptują wiele typów argumentów, w tym kolekcje zwracane z zapytań. Istnieją inne konstruktory i funkcje umożliwiające dodawanie zawartości XML.
ms.date: 07/20/2015
ms.assetid: 0d253586-2b97-459f-b1a7-f30f38f3ed9f
ms.openlocfilehash: e0288dce06f8040385c9b9a30335fd039d3c45bd
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553765"
---
# <a name="valid-content-of-xelement-and-xdocument-objects-linq-to-xml"></a><span data-ttu-id="b99f1-104">Prawidłowa zawartość obiektów XElement i XDocument (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="b99f1-104">Valid content of XElement and XDocument objects (LINQ to XML)</span></span>

<span data-ttu-id="b99f1-105">W tym artykule opisano prawidłowe argumenty, które mogą być przekazane do konstruktorów, oraz metody, które służą do dodawania zawartości do elementów i dokumentów.</span><span class="sxs-lookup"><span data-stu-id="b99f1-105">This article describes the valid arguments that can be passed to constructors, and methods that you use to add content to elements and documents.</span></span>

## <a name="valid-types-for-the-xelement-constructor"></a><span data-ttu-id="b99f1-106">Prawidłowe typy dla konstruktora XElement</span><span class="sxs-lookup"><span data-stu-id="b99f1-106">Valid types for the XElement constructor</span></span>

<span data-ttu-id="b99f1-107">Zapytania często są oceniane <xref:System.Collections.Generic.IEnumerable%601> do <xref:System.Xml.Linq.XElement> lub <xref:System.Collections.Generic.IEnumerable%601> z <xref:System.Xml.Linq.XAttribute> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-107">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="b99f1-108">Można przekazać kolekcje <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> obiekty do <xref:System.Xml.Linq.XElement> konstruktora.</span><span class="sxs-lookup"><span data-stu-id="b99f1-108">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="b99f1-109">Dlatego warto przekazać wyniki zapytania jako zawartość do metod i konstruktorów używanych do wypełniania drzew XML.</span><span class="sxs-lookup"><span data-stu-id="b99f1-109">That's why it's convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>

<span data-ttu-id="b99f1-110">Podczas dodawania prostej zawartości można przekazywać różne typy do tej metody, w tym:</span><span class="sxs-lookup"><span data-stu-id="b99f1-110">When adding simple content, various types can be passed to this method, including::</span></span>

- <xref:System.String>
- <xref:System.Double>
- <xref:System.Single>
- <xref:System.Decimal>
- <xref:System.Boolean>
- <xref:System.DateTime>
- <xref:System.TimeSpan>
- <xref:System.DateTimeOffset>
- <span data-ttu-id="b99f1-111">Dowolny typ, który implementuje `Object.ToString` .</span><span class="sxs-lookup"><span data-stu-id="b99f1-111">Any type that implements `Object.ToString`.</span></span>
- <span data-ttu-id="b99f1-112">Dowolny typ, który implementuje <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-112">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>

<span data-ttu-id="b99f1-113">Podczas dodawania zawartości złożonej różne typy mogą być przesyłane do tej metody, w tym:</span><span class="sxs-lookup"><span data-stu-id="b99f1-113">When adding complex content, various types can be passed to this method, including:</span></span>

- <xref:System.Xml.Linq.XObject>
- <xref:System.Xml.Linq.XNode>
- <xref:System.Xml.Linq.XAttribute>
- <span data-ttu-id="b99f1-114">Dowolny typ, który implementuje <xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="b99f1-114">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>

<span data-ttu-id="b99f1-115">Jeśli obiekt implementuje <xref:System.Collections.Generic.IEnumerable%601> , kolekcja w obiekcie jest wyliczana i dodawane są wszystkie elementy w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b99f1-115">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="b99f1-116">Jeśli kolekcja zawiera <xref:System.Xml.Linq.XNode> obiekty lub <xref:System.Xml.Linq.XAttribute> , każdy element w kolekcji zostanie dodany osobno.</span><span class="sxs-lookup"><span data-stu-id="b99f1-116">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="b99f1-117">Jeśli kolekcja zawiera tekst (lub obiekty, które są konwertowane na tekst), tekst w kolekcji zostanie połączony i dodany jako pojedynczy węzeł tekstowy.</span><span class="sxs-lookup"><span data-stu-id="b99f1-117">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>

<span data-ttu-id="b99f1-118">Jeśli zawartość jest `null` , nic nie jest dodawane.</span><span class="sxs-lookup"><span data-stu-id="b99f1-118">If content is `null`, nothing is added.</span></span> <span data-ttu-id="b99f1-119">Podczas przekazywania kolekcji elementy w kolekcji mogą być `null` .</span><span class="sxs-lookup"><span data-stu-id="b99f1-119">When passing a collection, items in the collection can be `null`.</span></span> <span data-ttu-id="b99f1-120">`null`Element w kolekcji nie ma wpływu na drzewo.</span><span class="sxs-lookup"><span data-stu-id="b99f1-120">A `null` item in the collection has no effect on the tree.</span></span>

<span data-ttu-id="b99f1-121">Dodany atrybut musi mieć unikatową nazwę w obrębie zawartego elementu.</span><span class="sxs-lookup"><span data-stu-id="b99f1-121">An added attribute must have a unique name within its containing element.</span></span>

<span data-ttu-id="b99f1-122">W przypadku dodawania <xref:System.Xml.Linq.XNode> lub <xref:System.Xml.Linq.XAttribute> obiektów, jeśli nowa zawartość nie ma elementu nadrzędnego, obiekty są po prostu dołączone do drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="b99f1-122">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="b99f1-123">Jeśli nowa zawartość jest już nadrzędna i jest częścią innego drzewa XML, Nowa zawartość jest klonowana, a nowo sklonowana zawartość jest dołączona do drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="b99f1-123">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>

## <a name="valid-types-for-the-xdocument-constructor"></a><span data-ttu-id="b99f1-124">Prawidłowe typy dla konstruktora XDocument</span><span class="sxs-lookup"><span data-stu-id="b99f1-124">Valid types for the XDocument constructor</span></span>

<span data-ttu-id="b99f1-125">Atrybuty i zawartość prosta nie mogą zostać dodane do dokumentu.</span><span class="sxs-lookup"><span data-stu-id="b99f1-125">Attributes and simple content can't be added to a document.</span></span>

<span data-ttu-id="b99f1-126">Nie ma wielu scenariuszy, które wymagają utworzenia <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-126">There aren't many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="b99f1-127">Zamiast tego można zazwyczaj utworzyć drzewa XML z <xref:System.Xml.Linq.XElement> węzłem głównym.</span><span class="sxs-lookup"><span data-stu-id="b99f1-127">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="b99f1-128">Jeśli użytkownik nie ma konkretnego wymagania dotyczącego tworzenia dokumentu (na przykład dlatego, że konieczne jest utworzenie instrukcji przetwarzania i komentarzy na najwyższym poziomie lub konieczność obsługi typów dokumentów), często jest wygodniejszy do użycia <xref:System.Xml.Linq.XElement> jako węzeł główny.</span><span class="sxs-lookup"><span data-stu-id="b99f1-128">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it's often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>

<span data-ttu-id="b99f1-129">Prawidłowe typy dla <xref:System.Xml.Linq.XDocument.%23ctor%2A> konstruktora obejmują następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="b99f1-129">Valid types for the <xref:System.Xml.Linq.XDocument.%23ctor%2A> constructor include the following:</span></span>

- <span data-ttu-id="b99f1-130">Zero lub jeden <xref:System.Xml.Linq.XDocumentType> obiekt.</span><span class="sxs-lookup"><span data-stu-id="b99f1-130">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="b99f1-131">Typy dokumentów muszą występować przed elementem.</span><span class="sxs-lookup"><span data-stu-id="b99f1-131">The document types must come before the element.</span></span>
- <span data-ttu-id="b99f1-132">Zero lub jeden element.</span><span class="sxs-lookup"><span data-stu-id="b99f1-132">Zero or one element.</span></span>
- <span data-ttu-id="b99f1-133">Zero lub więcej komentarzy.</span><span class="sxs-lookup"><span data-stu-id="b99f1-133">Zero or more comments.</span></span>
- <span data-ttu-id="b99f1-134">Zero lub więcej instrukcji przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="b99f1-134">Zero or more processing instructions.</span></span>
- <span data-ttu-id="b99f1-135">Zero lub więcej węzłów tekstowych, które zawierają tylko biały znak.</span><span class="sxs-lookup"><span data-stu-id="b99f1-135">Zero or more text nodes that contain only white space.</span></span>

## <a name="constructors-and-functions-for-adding-content"></a><span data-ttu-id="b99f1-136">Konstruktory i funkcje umożliwiające dodawanie zawartości</span><span class="sxs-lookup"><span data-stu-id="b99f1-136">Constructors and functions for adding content</span></span>

<span data-ttu-id="b99f1-137">Poniższe metody pozwalają dodać zawartość podrzędną do elementu <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> :</span><span class="sxs-lookup"><span data-stu-id="b99f1-137">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>

|<span data-ttu-id="b99f1-138">Metoda</span><span class="sxs-lookup"><span data-stu-id="b99f1-138">Method</span></span>|<span data-ttu-id="b99f1-139">Opis</span><span class="sxs-lookup"><span data-stu-id="b99f1-139">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|<span data-ttu-id="b99f1-140">Konstruuje <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-140">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|<span data-ttu-id="b99f1-141">Konstruuje a <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-141">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="b99f1-142">Dodaje do końca zawartości podrzędnej <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-142">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="b99f1-143">Dodaje zawartość po <xref:System.Xml.Linq.XNode> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-143">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="b99f1-144">Dodaje zawartość przed <xref:System.Xml.Linq.XNode> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-144">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="b99f1-145">Dodaje zawartość na początku zawartości podrzędnej <xref:System.Xml.Linq.XContainer> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-145">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|<span data-ttu-id="b99f1-146">Zamienia całą zawartość (węzły podrzędne i atrybuty) obiektu <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-146">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|<span data-ttu-id="b99f1-147">Zastępuje atrybuty <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="b99f1-147">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|<span data-ttu-id="b99f1-148">Zamienia węzły podrzędne na nową zawartość.</span><span class="sxs-lookup"><span data-stu-id="b99f1-148">Replaces the children nodes with new content.</span></span>|
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|<span data-ttu-id="b99f1-149">Zamienia węzeł na nową zawartość.</span><span class="sxs-lookup"><span data-stu-id="b99f1-149">Replaces a node with new content.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b99f1-150">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b99f1-150">See also</span></span>

- [<span data-ttu-id="b99f1-151">Drzewa XML</span><span class="sxs-lookup"><span data-stu-id="b99f1-151">XML trees</span></span>](functional-construction.md)
