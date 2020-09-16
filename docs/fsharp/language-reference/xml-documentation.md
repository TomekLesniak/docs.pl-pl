---
title: Dokumentacja XML
description: 'Dowiedz się więcej o pomocy technicznej w języku F # w celu wygenerowania dokumentacji z komentarzy.'
ms.date: 05/16/2016
ms.openlocfilehash: 03d14cef910d149f0c7a2f3a49c8cf4606ac5305
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556580"
---
# <a name="xml-documentation"></a>Dokumentacja XML

Można utworzyć dokumentację z komentarzy do kodu potrójnym ukośnikiem (//) w języku F #. Komentarze XML mogą poprzedzać deklaracje w plikach kodu (. FS) lub sygnatur (. FSI).

## <a name="generating-documentation-from-comments"></a>Generowanie dokumentacji z komentarzy

Pomoc techniczna w języku F # do generowania dokumentacji z komentarzy jest taka sama jak w innych językach .NET Framework. Podobnie jak w innych językach .NET Framework, [Opcja kompilatora-doc](./compiler-options.md) umożliwia tworzenie pliku XML, który zawiera informacje, które można skonwertować do dokumentacji przy użyciu narzędzia, takiego jak [DocFX](https://dotnet.github.io/docfx/) lub [Sandcastle](https://github.com/EWSoftware/SHFB). Dokumentacja wygenerowana przy użyciu narzędzi przeznaczonych do użytku z zestawami, które są napisane w innych językach .NET Framework zwykle przedstawia widok interfejsów API opartych na skompilowanej formie konstrukcji języka F #. Jeśli narzędzia nie obsługują języka F #, dokumentacja wygenerowana przez te narzędzia nie jest zgodna z widokiem języka F # interfejsu API.

Aby uzyskać więcej informacji o sposobach generowania dokumentacji z pliku XML, zobacz [Komentarze dokumentacji XML &#40;C&#35; Przewodnik programowania&#41;](../../csharp/programming-guide/xmldoc/index.md).

## <a name="recommended-tags"></a>Zalecane Tagi

Istnieją dwa sposoby zapisywania komentarzy do dokumentacji XML. Po prostu napisz dokumentację bezpośrednio w komentarzu z potrójnym ukośnikiem, bez używania tagów XML. Jeśli to zrobisz, cały tekst komentarza jest traktowany jako dokumentacja podsumowania konstrukcji kodu, która jest bezpośrednio następująca. Użyj tej metody, jeśli chcesz napisać tylko krótkie podsumowanie dla każdej konstrukcji. Druga metoda polega na użyciu tagów XML w celu zapewnienia większej dokumentacji strukturalnej. Druga metoda pozwala określić oddzielne notatki dla krótkiego podsumowania, dodatkowe uwagi, dokumentację dla każdego parametru i parametru typu oraz zgłoszone wyjątki oraz opis wartości zwracanej. W poniższej tabeli opisano tagi XML, które są rozpoznawane w komentarzach kodu XML w języku F #.

|Składnia tagów|Opis|
|----------|-----------|
|**\<c\>**_Opis_**\</c\>**|Określa, że *tekst* jest kodem. Ten tag może być używany przez generatory dokumentacji do wyświetlania tekstu w czcionce, która jest odpowiednia dla kodu.|
|**\<summary\>**_Opis_**\</summary\>**|Określa, że *tekst* jest krótkim opisem elementu programu. Opis jest zwykle jednym lub dwoma zdaniami.|
|**\<remarks\>**_Opis_**\</remarks\>**|Określa, że *tekst* zawiera dodatkowe informacje o elemencie program.|
|**\<param name="**_name_**"\>**_zharmonizowan_**\</param\>**|Określa nazwę i opis parametru funkcji lub metody.|
|**\<typeparam name="**_name_**"\>**_zharmonizowan_**\</typeparam\>**|Określa nazwę i opis parametru typu.|
|**\<returns\>**_Opis_**\</returns\>**|Określa, że *tekst* opisuje wartość zwracaną przez funkcję lub metodę.|
|**\<exception cref="**_type_**"\>**_zharmonizowan_**\</exception\>**|Określa typ wyjątku, który może być wygenerowany i okoliczności, w których jest generowany.|
|**\<see cref="**_reference_**"\>**_Opis_**\</see\>**|Określa link wbudowany do innego elementu programu. *Odwołanie* jest nazwą wyświetlaną w pliku dokumentacji XML. *Tekst* jest tekstem wyświetlanym w łączu.|
|**\<seealso cref="**_reference_**"/\>**|Określa również link do dokumentacji dla innego typu. *Odwołanie* jest nazwą wyświetlaną w pliku dokumentacji XML. Zobacz także linki zwykle wyświetlane w dolnej części strony dokumentacji.|
|**\<para\>**_Opis_**\</para\>**|Określa akapit tekstu. Służy do rozdzielania tekstu wewnątrz znacznika **uwagi** .|

## <a name="example"></a>Przykład

### <a name="description"></a>Opis

Poniżej znajduje się typowy komentarz dokumentacji XML w pliku sygnatury.

### <a name="code"></a>Kod

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>Przykład

### <a name="description"></a>Opis

Poniższy przykład pokazuje alternatywną metodę bez tagów XML. W tym przykładzie cały tekst w komentarzu jest traktowany jako podsumowanie. Należy pamiętać, że jeśli nie określisz jawnie tagu podsumowującego, nie należy określać innych tagów, takich jak **param** lub **zwracających** Tagi.

### <a name="code"></a>Kod

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka F #](index.md)
- [Opcje kompilatora](compiler-options.md)
