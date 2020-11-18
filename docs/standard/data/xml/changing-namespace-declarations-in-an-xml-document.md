---
title: Zmienianie deklaracji przestrzeni nazw w dokumencie XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: f4f081e1db2ccacf4714ad3009eefdfc290b2ed4
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821830"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Zmienianie deklaracji przestrzeni nazw w dokumencie XML
Element **XmlDocument** ujawnia deklaracje przestrzeni nazw i atrybuty **xmlns** w ramach modelu obiektów dokumentu. Są one przechowywane w **XmlDocument**, dlatego po zapisaniu dokumentu można zachować jego lokalizację. Zmiana tych atrybutów nie ma wpływu na właściwości **name**, **NamespaceURI** i **prefix** innych węzłów znajdujących się już w drzewie. Na przykład, Jeśli załadujesz następujący dokument, `test` element ma **NamespaceURI**`123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 Usunięcie `xmlns` atrybutu w następujący sposób oznacza, że `test` element nadal ma **NamespaceURI** `123` .  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Podobnie, jeśli dodasz inny `xmlns` atrybut do `doc` elementu w następujący sposób, `test` element nadal ma **NamespaceURI** `123` .  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 W związku z tym zmiana `xmlns` atrybutów nie będzie miała wpływu do momentu zapisania i ponownego załadowania obiektu **XmlDocument** .  
  
## <a name="see-also"></a>Zobacz także

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
