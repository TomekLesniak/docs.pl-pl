---
description: -moduleassemblyname — (opcja kompilatora C#)
title: -moduleassemblyname — (opcja kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
ms.openlocfilehash: 9131db17d767c76fe6a57f5d5353474153e0c269
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194092"
---
# <a name="-moduleassemblyname-c-compiler-option"></a>-moduleassemblyname — (opcja kompilatora C#)

Określa zestaw, którego typy niepubliczne a. module mogą uzyskać dostęp.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumenty  

 `assembly_name`  
 Nazwa zestawu, którego typy niepubliczne mogą uzyskać dostęp do modułu.  
  
## <a name="remarks"></a>Uwagi  

 **-moduleassemblyname —** należy używać podczas kompilowania modułu. sieci i, gdy są spełnione następujące warunki:  
  
- Moduł. Webmusi mieć dostęp do niepublicznych typów w istniejącym zestawie.  
  
- Znasz nazwę zestawu, do którego zostanie skompilowany moduł.  
  
- Istniejący zestaw przydzieli znajomemu dostęp do zestawu, do którego zostanie skompilowany moduł.  
  
 Aby uzyskać więcej informacji na temat tworzenia modułu., zobacz [-target: module (opcje kompilatora C#)](./target-module-compiler-option.md).  
  
 Aby uzyskać więcej informacji o znajomych zestawach, zobacz [zaprzyjaźnione zestawy](../../../standard/assembly/friend.md).  
  
 Ta opcja jest niedostępna w środowisku programistycznym; jest on dostępny tylko w przypadku kompilowania z wiersza polecenia.  
  
 Ta opcja kompilatora jest niedostępna w programie Visual Studio i nie można jej zmienić programowo.  
  
## <a name="example"></a>Przykład  

 Ten przykład kompiluje zestaw z typem prywatnym i zapewnia znajomemu dostęp do zestawu o nazwie csman_an_assembly.  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: -target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class
{  
    public void Test()
    {
        Console.WriteLine("An_Internal_Class.Test called");
    }  
}  
```  
  
## <a name="example"></a>Przykład  

 Ten przykład tworzy moduł. Service, który uzyskuje dostęp do typu niepublicznego w zestawie moduleassemblyname_1.dll. Wiedząc, że ten moduł. module zostanie skompilowany w zestawie o nazwie csman_an_assembly, możemy określić wartość **-moduleassemblyname —**, zezwalając na dostęp do niepublicznych typów w zestawie, który udzielił znajomemu dostęp do zestawu csman_an_assembly.  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: -moduleassemblyname:csman_an_assembly -target:module -reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a>Przykład  

 Ten przykładowy kod kompiluje csman_an_assembly zestawu, odwołujący się do poprzednio skompilowanego zestawu i modułu.  
  
```csharp  
// csman_an_assembly.cs  
// compile with: -addmodule:moduleassemblyname_2.netmodule -reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
**An_Internal_Class. test wywołany**

## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
