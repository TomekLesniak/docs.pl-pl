---
title: Łatwiejsze debugowanie obrazu w programie .NET
description: Informacje o konfigurowaniu obrazu wykonywalnego w celu łatwiejszego debugowania przy użyciu przełączników IDE i opcji wiersza polecenia.
ms.date: 08/30/2018
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
ms.openlocfilehash: a3305dc864e7852c2336009503732a51868410d2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558514"
---
# <a name="making-an-image-easier-to-debug-in-net"></a>Łatwiejsze debugowanie obrazu w programie .NET

Podczas kompilowania niezarządzanego kodu można za pomocą odpowiednich przełączników środowiska IDE lub opcji wiersza polecenia skonfigurować wykonywalny obraz na potrzeby debugowania. Na przykład można użyć opcji wiersza polecenia/**Zi** w Visual C++, aby zażądać jej do emitowania plików symboli debugowania (rozszerzenie pliku. pdb). Podobnie opcja wiersza polecenia/**od** instruuje kompilator, aby wyłączył optymalizację. Otrzymany kod działa wolniej, ale w razie potrzeby jest łatwiejszy do debugowania.

Podczas kompilowania .NET Framework kodu zarządzanego, kompilatory, takie jak Visual C++, Visual Basic i C# kompilują swój program źródłowy do języka pośredniego firmy Microsoft (MSIL). KOMPILATOR MSIL jest następnie kompilowany przed wykonaniem w kodzie macierzystym. Podobnie jak w przypadku kodu niezarządzanego za pomocą odpowiednich przełączników środowiska IDE lub opcji wiersza polecenia można na potrzeby debugowania skonfigurować wykonywalny obraz. Możesz również skonfigurować kompilację JIT w taki sam sposób, jak w przypadku debugowania.

Taka konfiguracja JIT ma dwa aspekty:

- Możesz zażądać kompilatora JIT, aby generować informacje o śledzeniu. Po włączeniu tej opcji debuger może porównywać łańcuch kodu języka MSIL z jego odpowiednikiem w kodzie maszynowym oraz śledzić, gdzie są przechowywane lokalne zmienne i argumenty funkcji. Począwszy od .NET Framework w wersji 2,0 kompilator JIT zawsze generuje informacje śledzenia, więc nie ma potrzeby żądania.

- Można zażądać kompilatora JIT, aby nie optymalizować powstającego kodu maszynowego.

Zwykle kompilator generujący MSIL ustawia te opcje kompilatora JIT odpowiednio na podstawie przełączników IDE lub opcji wiersza polecenia, które określisz, na przykład,/**od**.

Czasami trzeba zmienić zachowanie kompilatora JIT, tak aby generowany przez niego kod maszynowy był łatwiejszy do debugowania. Na przykład warto wygenerować informacje ze śledzenia kompilatora JIT dla kompilacji detalicznej lub optymalizacji kontrolek. Należy do tego celu użyć pliku inicjującego (.ini).

Na przykład jeśli zestaw, który ma być debugowany, jest nazywany *MyApp.exe*, można utworzyć plik tekstowy o nazwie *MyApp.ini*w tym samym folderze, w którym znajduje się *MyApp.exe*, który zawiera następujące trzy wiersze:

```ini
[.NET Framework Debugging Control]
GenerateTrackingInfo=1
AllowOptimize=0
```

Dla każdej opcji można ustawić wartość 0 lub 1. Każda niezdefiniowana opcja domyślnie przyjmuje wartość 0. Ustawienie w opcji `GenerateTrackingInfo` wartości 1 i w opcji `AllowOptimize` wartości 0 zapewni najłatwiejsze debugowanie.

Począwszy od .NET Framework w wersji 2,0, kompilator JIT zawsze generuje informacje o śledzeniu niezależnie od wartości `GenerateTrackingInfo` , jednak `AllowOptimize` nadal ma efekt. W przypadku korzystania z [Ngen.exe (Generator obrazu natywnego)](../tools/ngen-exe-native-image-generator.md) do wstępnego kompilowania obrazu natywnego bez optymalizacji, plik. ini musi znajdować się w folderze docelowym, `AllowOptimize=0` gdy jest wykonywana Ngen.exe. Jeśli wstępnie skompilowano zestaw bez optymalizacji, należy usunąć wstępnie skompilowany kod przy użyciu opcji NGen.exe **/Uninstall** przed ponownym uruchomieniem Ngen.exe, aby wstępnie skompilować kod jako zoptymalizowany. Jeśli plik. ini nie znajduje się w folderze, domyślnie Ngen.exe wstępnie kompiluje kod jako zoptymalizowany.

Klasa <xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> kontroluje ustawienia zestawu. **DebuggableAttribute** zawiera dwa pola, które kontrolują, czy kompilator JIT powinien optymalizować i/lub generować informacje śledzenia. Począwszy od .NET Framework w wersji 2,0 kompilator JIT zawsze generuje informacje o śledzeniu.

W przypadku kompilacji detalicznej kompilatory nie ustawiają żadnych **DebuggableAttribute**. Domyślnie kompilator JIT generuje najwyższy poziom wydajności, najtrudniejszy do debugowania kod maszynowy. Włączenie funkcji śledzenia w kompilatorze JIT obniża wydajność nieznacznie, natomiast wyłączenie optymalizacji zmniejsza ją wyraźnie.

**DebuggableAttribute** dotyczy całego zestawu jednocześnie, a nie do poszczególnych modułów w ramach zestawu. Narzędzia programistyczne muszą w związku z tym dołączać atrybuty niestandardowe do tokenu metadanych zestawu, jeśli zestaw został już utworzony, lub do klasy o nazwie **System. Runtime. CompilerServices. AssemblyAttributesGoHere**. Narzędzie ALink następnie promuje te atrybuty **DebuggableAttribute** z każdego modułu do zestawu, do którego należy. W razie wystąpienia konfliktu operacja ALink kończy się niepowodzeniem.

> [!NOTE]
> W wersji 1,0 .NET Framework, kompilator Microsoft Visual C++ dodaje **DebuggableAttribute** , gdy są określone opcje kompilatora **/CLR** i **/Zi** . W wersji 1,1 .NET Framework należy ręcznie dodać **DebuggableAttribute** w kodzie lub użyć opcji konsolidatora **/ASSEMBLYDEBUG** .

## <a name="see-also"></a>Zobacz także

- [Debugowanie, śledzenie i profilowanie](index.md)
- [Włączanie debugowania dołączania JIT](enabling-jit-attach-debugging.md)
- [Włączanie profilowania](/previous-versions/dotnet/netframework-4.0/s5ec0es1(v=vs.100))
