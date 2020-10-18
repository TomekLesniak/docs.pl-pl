---
title: Rozpocznij — wprowadzenie do języka C# i .NET "
description: Poznaj podstawy języków C# i .NET. Zapoznaj się z omówieniem języka C# i ekosystemu platformy .NET.
ms.date: 10/13/2020
ms.openlocfilehash: 94d49be28fbdba8f58ca16e959a10643d6467c63
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160961"
---
# <a name="introduction-to-the-c-language-and-net"></a>Wprowadzenie do języka C# i programu .NET

C# jest eleganckim i bezpiecznym dla typu językiem zorientowanym na obiekty. Język C# umożliwia deweloperom tworzenie wielu typów bezpiecznych i niezawodnych aplikacji, które działają w ekosystemie platformy .NET.

## <a name="c-language"></a>C# — język

Składnia języka C# jest wysoce jasno, ale jest również prosta i łatwa do uczenia się. Składnia języka C# w nawiasach klamrowych będzie natychmiast rozpoznawalna dla każdego znanego w języku C, C++, Java lub JavaScript. Deweloperzy, którzy znają którykolwiek z tych języków, zazwyczaj mogą wydajnie pracować w języku C# w krótkim czasie. Język C# zapewnia zaawansowane funkcje, takie jak typy dopuszczające wartości null, Delegaty, wyrażenia lambda, dopasowanie wzorców i bezpieczny bezpośredni dostęp do pamięci. Język C# obsługuje metody rodzajowe i typy, które zapewniają zwiększone bezpieczeństwo typu i wydajność. Język C# zawiera Iteratory, które umożliwiają implementacje klas kolekcji w celu zdefiniowania niestandardowych zachowań kodu klienta. Wyrażenia Language-Integrated Query (LINQ) czynią silnie wpisaną kwerendę dla konstrukcji języka pierwszej klasy.

Jako język zorientowany obiektowo, C# obsługuje koncepcje hermetyzacji, dziedziczenia i polimorfizmu. Klasa może dziedziczyć bezpośrednio z jednej klasy nadrzędnej, ale może implementować dowolną liczbę interfejsów. Metody, które zastępują metody wirtualne w klasie nadrzędnej, wymagają `override` słowa kluczowego jako sposobu, aby uniknąć przypadkowej ponownej definicji. W języku C# struktura jest taka sama jak Klasa uproszczona; jest to typ alokowany przez stos, który może implementować interfejsy, ale nie obsługuje dziedziczenia. Język C# zawiera również rekordy, które są typami klas, których celem jest przechowywanie głównie wartości danych.

Język C# ułatwia tworzenie składników oprogramowania za poorednictwem kilku innowacyjnych konstrukcji językowych, takich jak:

- Wyhermetyzowane sygnatury metod o nazwie *pełnomocnicy*, które włączają powiadomienia o zdarzeniach bezpiecznych dla typów.
- Właściwości, które stanowią metody dostępu do zmiennych prywatnych elementów członkowskich.
- Atrybuty, które zapewniają deklaratywne metadane dotyczące typów w czasie wykonywania.
- Komentarze do wbudowanej dokumentacji XML.
- Language-Integrated Query (LINQ), która udostępnia wbudowane funkcje zapytań w różnych rodzajach źródeł danych.
- Dopasowanie wzorca, które umożliwia sterowanie przepływem przez sprawdzanie typów danych i wartości.

Można korzystać ze składników natywnych za pomocą procesu o nazwie "Interop". Międzyoperacyjność umożliwia aplikacjom języka C# niemal wszystko, co można zrobić za pomocą natywnej aplikacji C++. Język C# obsługuje nawet wskaźniki i koncepcję niebezpiecznego kodu dla tych przypadków, w których bezpośredni dostęp do pamięci jest krytyczny.

Proces kompilacji w języku C# jest prosty w porównaniu z C i C++ i bardziej elastyczny niż w języku Java. Nie ma oddzielnych plików nagłówkowych i nie ma potrzeby deklarowania metod i typów w określonej kolejności. Plik źródłowy języka C# może definiować dowolną liczbę klas, struktur, interfejsów i zdarzeń.

Poniżej przedstawiono dodatkowe zasoby w języku C#:

- Aby zapoznać się z dobrymi ogólnymi wprowadzeniem do języka, zobacz [Przewodnik po języku C#](../tour-of-csharp/index.md).
- Aby uzyskać szczegółowe informacje na temat określonych aspektów języka C#, zobacz [Dokumentacja języka c#](../language-reference/index.md).
- Aby uzyskać więcej informacji na temat LINQ, zobacz [LINQ (zapytanie zintegrowane z językiem)](../programming-guide/concepts/linq/index.md).

## <a name="net-platform-architecture"></a>Architektura platformy .NET

Programy w języku C# działają w środowisku .NET, wirtualnym systemie wykonywania nazywanym środowiskiem uruchomieniowym języka wspólnego (CLR) i ujednoliconym zestawem bibliotek klas. Środowisko CLR to komercyjna implementacja infrastruktury Common Language Infrastructure (CLI), standard międzynarodowy. Interfejs wiersza polecenia jest podstawą do tworzenia środowisk wykonawczych i programistycznych, w których Języki i biblioteki współdziałają ze sobą bezproblemowo.

Kod źródłowy zapisany w języku C# jest kompilowany do [języka pośredniego (IL)](../../standard/managed-code.md) , który jest zgodny ze specyfikacją interfejsu wiersza polecenia. Kod IL i zasoby, takie jak mapy bitowe i ciągi, są przechowywane w zestawie, zazwyczaj z rozszerzeniem. dll. Zestaw zawiera manifest, który zawiera informacje o typach, wersji i kulturze zestawu.

Gdy program C# jest wykonywany, zestaw jest ładowany do środowiska CLR. Środowisko CLR wykonuje kompilację just-in-Time (JIT), aby przekonwertować kod IL na instrukcje maszyny natywnej. Środowisko CLR udostępnia inne usługi związane z automatycznym odzyskiwaniem pamięci, obsługą wyjątków i zarządzaniem zasobami. Kod wykonywany przez środowisko CLR jest czasami określany jako "kod zarządzany", w przeciwieństwie do "kodu niezarządzanego", który jest kompilowany do macierzystego języka maszynowego, który jest przeznaczony dla określonego systemu.

Współdziałanie języków jest kluczową funkcją platformy .NET. Kod IL tworzony przez kompilator języka C# jest zgodny ze specyfikacją Common Type Specification (CTS). Kod IL generowany na podstawie języka C# może współistnieć z kodem, który został wygenerowany na podstawie wersji .NET programu F #, Visual Basic, C++ lub dowolnych z ponad 20 innych języków zgodnych ze standardem CTS. Pojedynczy zestaw może zawierać wiele modułów pisanych w różnych językach .NET, a typy mogą się odwoływać nawzajem, tak jakby były zapisywane w tym samym języku.

Oprócz usług czasu wykonywania platforma .NET zawiera również rozbudowane biblioteki. Te biblioteki obsługują wiele różnych obciążeń. Są one zorganizowane w przestrzenie nazw, które zapewniają szeroką gamę użytecznych funkcji dla wszystkich elementów danych wejściowych i wyjściowych w celu manipulowania ciągami do analizy XML, do struktur aplikacji sieci Web w celu Windows Forms formantów. Typowa aplikacja C# używa biblioteki klas .NET w szerokim stopniu do obsługi typowych zadań "wodociągów".

Aby uzyskać więcej informacji na temat platformy .NET, zobacz [Omówienie platformy .NET](../../core/introduction.md).
