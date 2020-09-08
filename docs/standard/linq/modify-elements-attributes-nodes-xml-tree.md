---
title: Modyfikowanie elementów, atrybutów i węzłów w drzewie XML
description: Dowiedz się więcej o metodach i właściwościach, których można użyć do modyfikacji elementu, jego węzłów podrzędnych lub jego atrybutów.
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 671ba38350e443d95c92a9bd790eac3d2deb5cdd
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553747"
---
# <a name="modify-elements-attributes-and-nodes-in-an-xml-tree-linq-to-xml"></a><span data-ttu-id="1c987-103">Modyfikowanie elementów, atrybutów i węzłów w drzewie XML (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1c987-103">Modify elements, attributes, and nodes in an XML tree (LINQ to XML)</span></span>

<span data-ttu-id="1c987-104">Poniższa tabela zawiera podsumowanie metod i właściwości, których można użyć do modyfikacji elementu, jego elementów podrzędnych lub jego atrybutów.</span><span class="sxs-lookup"><span data-stu-id="1c987-104">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>

<span data-ttu-id="1c987-105">Następujące metody modyfikują <xref:System.Xml.Linq.XElement> :</span><span class="sxs-lookup"><span data-stu-id="1c987-105">The following methods modify an <xref:System.Xml.Linq.XElement>:</span></span>

|<span data-ttu-id="1c987-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="1c987-106">Method</span></span>|<span data-ttu-id="1c987-107">Opis</span><span class="sxs-lookup"><span data-stu-id="1c987-107">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-108">Zastępuje element przeanalizowanym kodem XML.</span><span class="sxs-lookup"><span data-stu-id="1c987-108">Replaces an element with parsed XML.</span></span>|
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-109">Usuwa całą zawartość (węzły podrzędne i atrybuty) elementu.</span><span class="sxs-lookup"><span data-stu-id="1c987-109">Removes all content (child nodes and attributes) of an element.</span></span>|
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-110">Usuwa atrybuty elementu.</span><span class="sxs-lookup"><span data-stu-id="1c987-110">Removes the attributes of an element.</span></span>|
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-111">Zamienia całą zawartość (węzły podrzędne i atrybuty) elementu.</span><span class="sxs-lookup"><span data-stu-id="1c987-111">Replaces all content (child nodes and attributes) of an element.</span></span>|
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-112">Zastępuje atrybuty elementu.</span><span class="sxs-lookup"><span data-stu-id="1c987-112">Replaces the attributes of an element.</span></span>|
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-113">Ustawia wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="1c987-113">Sets the value of an attribute.</span></span> <span data-ttu-id="1c987-114">Tworzy atrybut, jeśli nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="1c987-114">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="1c987-115">Jeśli wartość jest ustawiona na `null` , program usuwa atrybut.</span><span class="sxs-lookup"><span data-stu-id="1c987-115">If the value is set to `null`, removes the attribute.</span></span>|
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-116">Ustawia wartość elementu podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="1c987-116">Sets the value of a child element.</span></span> <span data-ttu-id="1c987-117">Tworzy element, jeśli nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="1c987-117">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="1c987-118">Jeśli wartość jest ustawiona na `null` , powoduje usunięcie elementu.</span><span class="sxs-lookup"><span data-stu-id="1c987-118">If the value is set to `null`, removes the element.</span></span>|
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-119">Zamienia zawartość (węzły podrzędne) elementu na określony tekst.</span><span class="sxs-lookup"><span data-stu-id="1c987-119">Replaces the content (child nodes) of an element with the specified text.</span></span>|
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-120">Ustawia wartość elementu.</span><span class="sxs-lookup"><span data-stu-id="1c987-120">Sets the value of an element.</span></span>|

<span data-ttu-id="1c987-121">Następujące metody modyfikują <xref:System.Xml.Linq.XAttribute> :</span><span class="sxs-lookup"><span data-stu-id="1c987-121">The following methods modify an <xref:System.Xml.Linq.XAttribute>:</span></span>

|<span data-ttu-id="1c987-122">Metoda</span><span class="sxs-lookup"><span data-stu-id="1c987-122">Method</span></span>|<span data-ttu-id="1c987-123">Opis</span><span class="sxs-lookup"><span data-stu-id="1c987-123">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-124">Ustawia wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="1c987-124">Sets the value of an attribute.</span></span>|
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-125">Ustawia wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="1c987-125">Sets the value of an attribute.</span></span>|

 <span data-ttu-id="1c987-126">Następujące metody modyfikują <xref:System.Xml.Linq.XNode> (łącznie z <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> ):</span><span class="sxs-lookup"><span data-stu-id="1c987-126">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>):</span></span>

|<span data-ttu-id="1c987-127">Metoda</span><span class="sxs-lookup"><span data-stu-id="1c987-127">Method</span></span>|<span data-ttu-id="1c987-128">Opis</span><span class="sxs-lookup"><span data-stu-id="1c987-128">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-129">Zamienia węzeł na nową zawartość.</span><span class="sxs-lookup"><span data-stu-id="1c987-129">Replaces a node with new content.</span></span>|

 <span data-ttu-id="1c987-130">Następujące metody modyfikują <xref:System.Xml.Linq.XContainer> ( <xref:System.Xml.Linq.XElement> a lub <xref:System.Xml.Linq.XDocument> ):</span><span class="sxs-lookup"><span data-stu-id="1c987-130">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>):</span></span>

|<span data-ttu-id="1c987-131">Metoda</span><span class="sxs-lookup"><span data-stu-id="1c987-131">Method</span></span>|<span data-ttu-id="1c987-132">Opis</span><span class="sxs-lookup"><span data-stu-id="1c987-132">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="1c987-133">Zastępuje węzły podrzędne nową zawartością:</span><span class="sxs-lookup"><span data-stu-id="1c987-133">Replaces the children nodes with new content:</span></span>|
