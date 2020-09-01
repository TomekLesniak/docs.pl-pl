---
description: Odwołanie wewnętrzne-C#
title: Odwołanie wewnętrzne-C#
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: 14722d66a65eb5f96118acf017dc877e657b2dd9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134578"
---
# <a name="internal-c-reference"></a>internal (odwołanie w C#)
`internal`Słowo kluczowe jest [modyfikatorem dostępu](./access-modifiers.md) dla typów i elementów członkowskich typu.
  
 > Ta strona dotyczy `internal` dostępu. `internal`Słowo kluczowe jest również częścią [`protected internal`](./protected-internal.md) modyfikatora dostępu.
  
Typy wewnętrzne lub składowe są dostępne tylko w plikach w tym samym zestawie, jak w poniższym przykładzie:  
  
```csharp  
public class BaseClass
{  
    // Only accessible within the same assembly.
    internal static int x = 0;
}  
```  

 Aby uzyskać porównanie `internal` z innymi modyfikatorami dostępu, zobacz [poziomy dostępności](./accessibility-levels.md) i [Modyfikatory dostępu](../../programming-guide/classes-and-structs/access-modifiers.md).  
  
 Aby uzyskać więcej informacji o zestawach, zobacz [zestawy w programie .NET](../../../standard/assembly/index.md).  
  
 Typowym zastosowaniem dostępu wewnętrznego jest w programowaniu opartym na składnikach, ponieważ umożliwia ono grupom współdziałanie w sposób prywatny bez ujawniania pozostałej części kodu aplikacji. Na przykład struktura do tworzenia graficznych interfejsów użytkownika mogłaby udostępniać `Control` klasy i `Form` współdziałać z użytkownikami z dostępem wewnętrznym. Ponieważ te składowe są wewnętrzne, nie są one widoczne dla kodu, który używa struktury.  
  
 Wystąpił błąd podczas odwoływania się do typu lub elementu członkowskiego z dostępem wewnętrznym poza zestawem, w ramach którego został zdefiniowany.  
  
## <a name="example"></a>Przykład  
 Ten przykład zawiera dwa pliki `Assembly1.cs` i `Assembly1_a.cs` . Pierwszy plik zawiera wewnętrzną klasę bazową `BaseClass` . W drugim pliku próba wystąpienia `BaseClass` spowoduje wystąpienie błędu.  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a>Przykład  
 W tym przykładzie należy użyć tych samych plików, które zostały użyte w przykładzie 1, i zmienić poziom dostępności `BaseClass` na `public` . Zmień również poziom dostępności elementu członkowskiego `intM` na `internal` . W takim przypadku można utworzyć wystąpienie klasy, ale nie można uzyskać dostępu do wewnętrznego elementu członkowskiego.  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a>Specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [zadeklarowane ułatwienia dostępu](~/_csharplang/spec/basic-concepts.md#declared-accessibility) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
- [Modyfikatory dostępu](./access-modifiers.md)
- [Poziomy ułatwień dostępu](./accessibility-levels.md)
- [Modyfikatory](index.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)
