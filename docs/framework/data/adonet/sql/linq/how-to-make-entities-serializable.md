---
title: 'Instrukcje: Umożliwianie serializacji jednostek'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: f4528cab21ac678f5d06717d0ce6e7ff7e77d3e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203504"
---
# <a name="how-to-make-entities-serializable"></a>Instrukcje: Umożliwianie serializacji jednostek

Jednostki można serializować podczas generowania kodu. Klasy jednostek są dekoracyjne <xref:System.Runtime.Serialization.DataContractAttribute> i są kolumnami z <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutem.  
  
 Deweloperzy korzystający z programu Visual Studio mogą w tym celu używać Object Relational Designer.  
  
 Jeśli używasz narzędzia wiersza polecenia SQLMetal, użyj opcji **/Serialization** z `unidirectional` argumentem. Aby uzyskać więcej informacji, zobacz [SqlMetal.exe (Narzędzie generowania kodu)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Przykład  

 Następujące wiersze poleceń SQLMetal tworzą pliki, które mają możliwe do serializacji jednostki.  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Zobacz też

- [Serializacja](serialization.md)
- [Tworzenie modelu obiektu](creating-the-object-model.md)
