---
title: Typizowane elementy DataSet
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 4648d49b1d7419d61a3a000404f42e0d02d25786
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198450"
---
# <a name="typed-datasets"></a><span data-ttu-id="c1b5d-102">Typizowane elementy DataSet</span><span class="sxs-lookup"><span data-stu-id="c1b5d-102">Typed DataSets</span></span>

<span data-ttu-id="c1b5d-103">Wraz z późnym wiązaniem dostępu do wartości za pomocą zmiennych o <xref:System.Data.DataSet> nieprawidłowym typie, zapewnia dostęp do danych przez silnie wpisaną metaphor.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="c1b5d-104">Do tabel i kolumn, które są częścią **zestawu danych** , można uzyskać dostęp przy użyciu nazw przyjaznych dla użytkownika i silnie wpisanych zmiennych.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="c1b5d-105">Typ **DataSet** jest klasą pochodzącą z **zestawu danych**.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="c1b5d-106">W związku z tym dziedziczy wszystkie metody, zdarzenia i właściwości **zestawu danych**.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="c1b5d-107">Ponadto typ **DataSet** zawiera silnie wpisane metody, zdarzenia i właściwości.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="c1b5d-108">Oznacza to, że można uzyskać dostęp do tabel i kolumn według nazwy, zamiast korzystać z metod opartych na kolekcji.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="c1b5d-109">Oprócz ulepszonego czytelności kodu, wpisany **zestaw danych** umożliwia również edytorowi kodu Visual Studio .net automatyczne uzupełnianie wierszy podczas pisania.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="c1b5d-110">Ponadto **zestaw danych** o jednoznacznie określonym typie zapewnia dostęp do wartości jako poprawnego typu w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="c1b5d-111">Przy użyciu silnie określonego **zestawu danych**błędy niezgodności typów są przechwytywane podczas kompilowania kodu, a nie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1b5d-112">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="c1b5d-112">In This Section</span></span>  

 [<span data-ttu-id="c1b5d-113">Generowanie silnie typizowanych elementów DataSet</span><span class="sxs-lookup"><span data-stu-id="c1b5d-113">Generating Strongly Typed DataSets</span></span>](generating-strongly-typed-datasets.md)  
 <span data-ttu-id="c1b5d-114">Opisuje sposób tworzenia i używania silnie określonego **zestawu danych**.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="c1b5d-115">Dodawanie adnotacji do typizowanych elementów DataSet</span><span class="sxs-lookup"><span data-stu-id="c1b5d-115">Annotating Typed DataSets</span></span>](annotating-typed-datasets.md)  
 <span data-ttu-id="c1b5d-116">Opisuje sposób dodawania adnotacji do schematu języka definicji schematu XML (XSD) używanego do generowania **zestawu danych**o jednoznacznie określonym typie, aby nadać elementom **DataSet** przyjazne nazwy bez modyfikowania bazowego schematu.</span><span class="sxs-lookup"><span data-stu-id="c1b5d-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1b5d-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c1b5d-117">See also</span></span>

- [<span data-ttu-id="c1b5d-118">Elementy DataSet, DataTable i DataView</span><span class="sxs-lookup"><span data-stu-id="c1b5d-118">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c1b5d-119">Omówienie ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c1b5d-119">ADO.NET Overview</span></span>](../ado-net-overview.md)
