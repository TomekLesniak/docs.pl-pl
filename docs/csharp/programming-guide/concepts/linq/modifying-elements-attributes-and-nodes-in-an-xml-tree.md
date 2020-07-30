---
title: Modyfikowanie elementów, atrybutów i węzłów w drzewie XML
description: Dowiedz się więcej o metodach i właściwościach, których można użyć do modyfikacji elementu, jego węzłów podrzędnych lub jego atrybutów.
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: bfff882dc57a4f6f4b228563ac923122097d88d0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303169"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="29dbe-103">Modyfikowanie elementów, atrybutów i węzłów w drzewie XML</span><span class="sxs-lookup"><span data-stu-id="29dbe-103">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="29dbe-104">Poniższa tabela zawiera podsumowanie metod i właściwości, których można użyć do modyfikacji elementu, jego elementów podrzędnych lub jego atrybutów.</span><span class="sxs-lookup"><span data-stu-id="29dbe-104">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="29dbe-105">Poniższe metody modyfikują <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="29dbe-105">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="29dbe-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="29dbe-106">Method</span></span>|<span data-ttu-id="29dbe-107">Opis</span><span class="sxs-lookup"><span data-stu-id="29dbe-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-108">Zastępuje element przeanalizowanym kodem XML.</span><span class="sxs-lookup"><span data-stu-id="29dbe-108">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-109">Usuwa całą zawartość (węzły podrzędne i atrybuty) elementu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-109">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-110">Usuwa atrybuty elementu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-110">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-111">Zamienia całą zawartość (węzły podrzędne i atrybuty) elementu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-111">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-112">Zastępuje atrybuty elementu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-112">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-113">Ustawia wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-113">Sets the value of an attribute.</span></span> <span data-ttu-id="29dbe-114">Tworzy atrybut, jeśli nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="29dbe-114">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="29dbe-115">Jeśli wartość jest ustawiona na `null` , program usuwa atrybut.</span><span class="sxs-lookup"><span data-stu-id="29dbe-115">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-116">Ustawia wartość elementu podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="29dbe-116">Sets the value of a child element.</span></span> <span data-ttu-id="29dbe-117">Tworzy element, jeśli nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="29dbe-117">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="29dbe-118">Jeśli wartość jest ustawiona na `null` , powoduje usunięcie elementu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-118">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-119">Zamienia zawartość (węzły podrzędne) elementu na określony tekst.</span><span class="sxs-lookup"><span data-stu-id="29dbe-119">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-120">Ustawia wartość elementu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-120">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="29dbe-121">Poniższe metody modyfikują <xref:System.Xml.Linq.XAttribute> .</span><span class="sxs-lookup"><span data-stu-id="29dbe-121">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="29dbe-122">Metoda</span><span class="sxs-lookup"><span data-stu-id="29dbe-122">Method</span></span>|<span data-ttu-id="29dbe-123">Opis</span><span class="sxs-lookup"><span data-stu-id="29dbe-123">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-124">Ustawia wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-124">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-125">Ustawia wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="29dbe-125">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="29dbe-126">Następujące metody modyfikują <xref:System.Xml.Linq.XNode> (łącznie z <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> ).</span><span class="sxs-lookup"><span data-stu-id="29dbe-126">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="29dbe-127">Metoda</span><span class="sxs-lookup"><span data-stu-id="29dbe-127">Method</span></span>|<span data-ttu-id="29dbe-128">Opis</span><span class="sxs-lookup"><span data-stu-id="29dbe-128">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-129">Zamienia węzeł na nową zawartość.</span><span class="sxs-lookup"><span data-stu-id="29dbe-129">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="29dbe-130">Następujące metody modyfikują <xref:System.Xml.Linq.XContainer> ( <xref:System.Xml.Linq.XElement> a lub <xref:System.Xml.Linq.XDocument> ).</span><span class="sxs-lookup"><span data-stu-id="29dbe-130">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="29dbe-131">Metoda</span><span class="sxs-lookup"><span data-stu-id="29dbe-131">Method</span></span>|<span data-ttu-id="29dbe-132">Opis</span><span class="sxs-lookup"><span data-stu-id="29dbe-132">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="29dbe-133">Zamienia węzły podrzędne na nową zawartość.</span><span class="sxs-lookup"><span data-stu-id="29dbe-133">Replaces the children nodes with new content.</span></span>|  
