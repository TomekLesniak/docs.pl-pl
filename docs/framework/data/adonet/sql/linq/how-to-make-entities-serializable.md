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
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="72ba1-102">Instrukcje: Umożliwianie serializacji jednostek</span><span class="sxs-lookup"><span data-stu-id="72ba1-102">How to: Make Entities Serializable</span></span>

<span data-ttu-id="72ba1-103">Jednostki można serializować podczas generowania kodu.</span><span class="sxs-lookup"><span data-stu-id="72ba1-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="72ba1-104">Klasy jednostek są dekoracyjne <xref:System.Runtime.Serialization.DataContractAttribute> i są kolumnami z <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutem.</span><span class="sxs-lookup"><span data-stu-id="72ba1-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="72ba1-105">Deweloperzy korzystający z programu Visual Studio mogą w tym celu używać Object Relational Designer.</span><span class="sxs-lookup"><span data-stu-id="72ba1-105">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="72ba1-106">Jeśli używasz narzędzia wiersza polecenia SQLMetal, użyj opcji **/Serialization** z `unidirectional` argumentem.</span><span class="sxs-lookup"><span data-stu-id="72ba1-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="72ba1-107">Aby uzyskać więcej informacji, zobacz [SqlMetal.exe (Narzędzie generowania kodu)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="72ba1-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="72ba1-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="72ba1-108">Example</span></span>  

 <span data-ttu-id="72ba1-109">Następujące wiersze poleceń SQLMetal tworzą pliki, które mają możliwe do serializacji jednostki.</span><span class="sxs-lookup"><span data-stu-id="72ba1-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="72ba1-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="72ba1-110">See also</span></span>

- [<span data-ttu-id="72ba1-111">Serializacja</span><span class="sxs-lookup"><span data-stu-id="72ba1-111">Serialization</span></span>](serialization.md)
- [<span data-ttu-id="72ba1-112">Tworzenie modelu obiektu</span><span class="sxs-lookup"><span data-stu-id="72ba1-112">Creating the Object Model</span></span>](creating-the-object-model.md)
