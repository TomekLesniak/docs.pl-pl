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
# <a name="how-to-build-linq-to-xml-examples"></a>Sposób kompilowania przykładów LINQ to XML

Fragmenty kodu i przykłady w tej dokumentacji używają klas i typów z różnych przestrzeni nazw. Podczas kompilowania kodu w języku C# należy podawać odpowiednie `using` dyrektywy i podczas kompilowania kodu Visual Basic należy dostarczyć odpowiednie `Imports` instrukcje.

## <a name="example"></a>Przykład

Poniższy kod zawiera `using` dyrektywy, których przykłady w języku C# wymagają do skompilowania i uruchomienia. Nie wszystkie `using` dyrektywy są wymagane dla każdego przykładu.

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

Poniższy kod zawiera `Imports` instrukcje, których przykłady Visual Basic wymagają do skompilowania i uruchomienia. Nie wszystkie `Imports` instrukcje są wymagane dla każdego przykładu.

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

## <a name="see-also"></a>Zobacz też

- [Przegląd LINQ to XML](linq-xml-overview.md)
