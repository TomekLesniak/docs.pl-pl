---
title: Sposób kompilowania przykładów LINQ to XML
description: Kod C# i Visual Basic w tej dokumentacji używają klas i typów z różnych przestrzeni nazw. Aby skompilować i uruchomić kod, musisz dostarczyć odpowiednie dyrektywy i instrukcje w celu uzyskania dostępu do przestrzeni nazw.
ms.date: 07/20/2015
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
ms.openlocfilehash: 94b2368e2c861f84d7db08fbbba57ef0f0da4d40
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553035"
---
# <a name="how-to-build-linq-to-xml-examples"></a><span data-ttu-id="3e2e8-104">Sposób kompilowania przykładów LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="3e2e8-104">How to build LINQ to XML examples</span></span>

<span data-ttu-id="3e2e8-105">Fragmenty kodu i przykłady w tej dokumentacji używają klas i typów z różnych przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-105">The snippets and examples in this documentation use classes and types from various namespaces.</span></span> <span data-ttu-id="3e2e8-106">Podczas kompilowania kodu w języku C# należy podawać odpowiednie `using` dyrektywy i podczas kompilowania kodu Visual Basic należy dostarczyć odpowiednie `Imports` instrukcje.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-106">When compiling C# code you need to supply appropriate `using` directives, and when compiling Visual Basic code you need to supply appropriate `Imports` statements.</span></span>

## <a name="example"></a><span data-ttu-id="3e2e8-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="3e2e8-107">Example</span></span>

<span data-ttu-id="3e2e8-108">Poniższy kod zawiera `using` dyrektywy, których przykłady w języku C# wymagają do skompilowania i uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-108">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="3e2e8-109">Nie wszystkie `using` dyrektywy są wymagane dla każdego przykładu.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-109">Not all `using` directives are required for every example.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Collections;
using System.Collections.Generic;
using System.Collections.Specialized;
using System.Text;
using System.Linq;
using System.Xml;
using System.Xml.Linq;
using System.Xml.Schema;
using System.Xml.XPath;
using System.Xml.Xsl;
using System.IO;
using System.Threading;
using System.Reflection;
using System.IO.Packaging;
```

<span data-ttu-id="3e2e8-110">Poniższy kod zawiera `Imports` instrukcje, których przykłady Visual Basic wymagają do skompilowania i uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-110">The following code contains the `Imports` statements that the Visual Basic examples require to build and run.</span></span> <span data-ttu-id="3e2e8-111">Nie wszystkie `Imports` instrukcje są wymagane dla każdego przykładu.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-111">Not all `Imports` statements are required for every example.</span></span>

```vb
Imports System.Diagnostics
Imports System.Collections
Imports System.Collections.Generic
Imports System.Collections.Specialized
Imports System.Text
Imports System.Linq
Imports System.Xml
Imports System.Xml.Linq
Imports System.Xml.Schema
Imports System.Xml.XPath
Imports System.Xml.Xsl
Imports System.IO
Imports System.Threading
Imports System.Reflection
Imports System.IO.Packaging
```

## <a name="see-also"></a><span data-ttu-id="3e2e8-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3e2e8-112">See also</span></span>

- [<span data-ttu-id="3e2e8-113">Przegląd LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="3e2e8-113">LINQ to XML overview</span></span>](linq-xml-overview.md)
