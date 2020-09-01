---
description: '#Dokumentacja wiersza — C#'
title: '#Dokumentacja wiersza — C#'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: e2a5ecb6c29184123b8a88ae1b12caf24ec7296a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137997"
---
# <a name="line-c-reference"></a>#line (odwołanie w C#)

`#line` umożliwia zmodyfikowanie numeracji linii kompilatora oraz (opcjonalnie) dane wyjściowe nazwy pliku dla błędów i ostrzeżeń.

Poniższy przykład pokazuje, jak zgłosić dwa ostrzeżenia skojarzone z numerami wierszy. `#line 200`Dyrektywa wymusza numer następnego wiersza do 200 (mimo że wartość domyślna to #6), a do następnej `#line` dyrektywy nazwa pliku będzie raportowana jako "Specjalna". `#line default`Dyrektywa zwraca numery wierszy do domyślnej numeracji, która zlicza wiersze, które zostały zmienione przez poprzednią dyrektywę.

```csharp
class MainClass
{
    static void Main()
    {
#line 200 "Special"
        int i;
        int j;
#line default
        char c;
        float f;
#line hidden // numbering not affected
        string s;
        double d;
    }
}
```

Kompilacja generuje następujące dane wyjściowe:

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
```

## <a name="remarks"></a>Uwagi

`#line`Dyrektywa może być używana w zautomatyzowanym, pośrednim kroku w procesie kompilacji. Na przykład jeśli linie zostały usunięte z oryginalnego pliku kodu źródłowego, ale nadal chcesz, aby kompilator generował dane wyjściowe na podstawie pierwotnej numeracji wierszy w pliku, możesz usunąć linie, a następnie symulować pierwotne numery wierszy przy użyciu `#line` .

`#line hidden`Dyrektywa powoduje ukrycie kolejnych wierszy w debugerze, takich jak w przypadku kroków wykonywanych przez dewelopera w kodzie, wszelkich wierszy między `#line hidden` a i Następna `#line` dyrektywa (przy założeniu, że nie jest to inna `#line hidden` dyrektywa) zostanie przełączona. Tej opcji można również użyć, aby zezwolić ASP.NET na rozróżnienie między zdefiniowanym przez użytkownika i generowanym przez maszyną kodem. Chociaż ASP.NET jest głównym odbiorcą tej funkcji, prawdopodobnie będzie ona używać większej liczby generatorów źródeł.

`#line hidden`Dyrektywa nie ma wpływu na nazwy plików lub numery wierszy w raportowaniu błędów. Oznacza to, że jeśli w ukrytym bloku wystąpi błąd, kompilator zgłosi bieżącą nazwę pliku i numer wiersza błędu.

`#line filename`Dyrektywa określa nazwę pliku, który ma być wyświetlany w danych wyjściowych kompilatora. Domyślnie używana jest rzeczywista nazwa pliku kodu źródłowego. Nazwa pliku musi być ujęta w znaki podwójnego cudzysłowu ("") i musi być poprzedzona numerem wiersza.

Plik kodu źródłowego może zawierać dowolną liczbę `#line` dyrektyw.

## <a name="example-1"></a>Przykład 1

Poniższy przykład pokazuje, jak debuger ignoruje ukryte wiersze w kodzie. Po uruchomieniu przykładu zostanie wyświetlonych trzy wiersze tekstu. Jeśli jednak ustawisz punkt przerwania, jak pokazano w przykładzie i naciśniesz klawisz F10, aby przejść przez kod, zobaczysz, że debuger ignoruje ukrytą linię. Zwróć również uwagę, że nawet jeśli ustawisz punkt przerwania w wierszu ukrytym, debuger nadal go zignoruje.

```csharp
// preprocessor_linehidden.cs
using System;
class MainClass
{
    static void Main()
    {
        Console.WriteLine("Normal line #1."); // Set break point here.
#line hidden
        Console.WriteLine("Hidden line.");
#line default
        Console.WriteLine("Normal line #2.");
    }
}
```

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
