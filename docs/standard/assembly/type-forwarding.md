---
title: Przekazywanie dalej typu w środowisku uruchomieniowym języka wspólnego
description: Przekazywanie typu pozwala przenieść typ do innego zestawu platformy .NET bez konieczności ponownego kompilowania aplikacji, które używają oryginalnego zestawu.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: cd166068993fb5d1a5164615de3926a06dda8098
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687669"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Przekazywanie dalej typu w środowisku uruchomieniowym języka wspólnego

Przekazywanie typu pozwala przenieść typ do innego zestawu bez konieczności ponownego kompilowania aplikacji, które używają oryginalnego zestawu.  
  
 Załóżmy na przykład, że aplikacja używa `Example` klasy w zestawie o nazwie *Utility.dll* . Deweloperzy *Utility.dll* mogą zdecydować się na refaktoryzację zestawu, a w procesie może przenieść `Example` klasę do innego zestawu. Jeśli stara wersja *Utility.dll* jest zastępowana przez nową wersję *Utility.dll* i jej zestawu towarzyszącego, aplikacja, która używa `Example` klasy, zakończy się niepowodzeniem, ponieważ nie może zlokalizować `Example` klasy w nowej wersji *Utility.dll* .  
  
 Deweloperzy *Utility.dll* mogą tego uniknąć przez przekazywanie żądań dla `Example` klasy przy użyciu <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> atrybutu. Jeśli atrybut został zastosowany do nowej wersji *Utility.dll* , żądania dotyczące `Example` klasy są przekazywane do zestawu, który zawiera teraz klasę. Istniejąca aplikacja nadal działa normalnie, bez ponownej kompilacji.

## <a name="forward-a-type"></a>Przekazywanie typu

 Aby przesłać dalej typ, należy wykonać cztery kroki:  
  
1. Przenieś kod źródłowy dla typu z oryginalnego zestawu do zestawu docelowego.  

2. W zestawie, w którym używany jest typ, Dodaj <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> dla typu, który został przeniesiony. Poniższy kod przedstawia atrybut dla typu o nazwie `Example` , który został przeniesiony.  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. Kompiluj zestaw, który zawiera teraz typ.  

4. Ponownie skompiluj zestaw, w którym znajduje się typ, z odwołaniem do zestawu, który zawiera teraz typ. Na przykład, Jeśli kompilujesz plik C# z wiersza polecenia, użyj opcji [-Reference (opcje kompilatora C#)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) , aby określić zestaw, który zawiera typ. W języku C++ Użyj dyrektywy [#using](/cpp/preprocessor/hash-using-directive-cpp) w pliku źródłowym, aby określić zestaw, który zawiera typ.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [Przekazywanie dalej typu (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)
- [#using — dyrektywa](/cpp/preprocessor/hash-using-directive-cpp)
