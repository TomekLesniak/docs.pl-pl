---
description: '#pragma checksum — odwołanie w C#'
title: '#pragma checksum — odwołanie w C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 60c491000337fd50da217e97054e86faccb2e7d7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137984"
---
# <a name="pragma-checksum-c-reference"></a>#pragma checksum (odwołanie w C#)
Generuje sumy kontrolne dla plików źródłowych, aby pomóc w debugowaniu stron ASP.NET.  
  
## <a name="syntax"></a>Składnia  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a>Parametry  
 `"filename"`  
 Nazwa pliku, który wymaga monitorowania pod kątem zmian lub aktualizacji.  
  
 `"{guid}"`  
 Unikatowy identyfikator globalny (GUID) algorytmu wyznaczania wartości skrótu.  
  
 `"checksum_bytes"`  
 Ciąg cyfr szesnastkowych reprezentujących bajty sum kontrolnych. Musi być parzystą liczbą cyfr szesnastkowych. Nieparzysta liczba cyfr skutkuje ostrzeżeniem w czasie kompilacji, a dyrektywa jest ignorowana.  
  
## <a name="remarks"></a>Uwagi  
 Debuger programu Visual Studio używa sumy kontrolnej, aby upewnić się, że zawsze znajdzie prawidłowe źródło. Kompilator oblicza sumę kontrolną pliku źródłowego, a następnie emituje dane wyjściowe do pliku bazy danych programu (PDB). Debuger następnie używa pliku PDB do porównania z sumą kontrolną, która jest obliczana dla plików źródłowych.  
  
 To rozwiązanie nie działa w przypadku projektów ASP.NET, ponieważ obliczona suma kontrolna jest dla wygenerowanego pliku źródłowego, a nie pliku. aspx. Aby rozwiązać ten problem, program `#pragma checksum` zapewnia obsługę sum kontrolnych dla stron ASP.NET.  
  
 Podczas tworzenia projektu ASP.NET w programie Visual C# wygenerowany plik źródłowy zawiera sumę kontrolną dla pliku. aspx, z którego jest generowane źródło. Następnie kompilator zapisuje te informacje w pliku PDB.  
  
 Jeśli kompilator napotka brak `#pragma checksum` dyrektywy w pliku, oblicza sumę kontrolną i zapisuje wartość do pliku PDB.  
  
## <a name="example"></a>Przykład  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Dyrektywy preprocesora języka C#](./index.md)
