---
title: Tworzenie i zgłaszanie wyjątków — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat tworzenia i zgłaszania wyjątków. Wyjątki są używane do wskazywania, że wystąpił błąd podczas uruchamiania programu.
ms.date: 07/20/2015
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
ms.openlocfilehash: 8ab10dbf686def8d169ef3239492e3b618e9d297
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302051"
---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a>Tworzenie i zgłaszanie wyjątków (Przewodnik programowania w języku C#)
Wyjątki są używane do wskazywania, że wystąpił błąd podczas uruchamiania programu. Obiekty wyjątków opisujące błąd są tworzone, a następnie *generowane* za pomocą słowa kluczowego [throw](../../language-reference/keywords/throw.md) . Środowisko uruchomieniowe następnie wyszukuje najbardziej zgodny program obsługi wyjątków.  
  
 Programiści powinni zgłosić wyjątki, gdy spełnione są co najmniej jeden z następujących warunków:  
  
- Metoda nie może ukończyć zdefiniowanej funkcji.  
  
     Na przykład jeśli parametr do metody ma nieprawidłową wartość:  
  
     [!code-csharp[csProgGuideExceptions#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#12)]  
  
- Nieodpowiednie wywołanie do obiektu jest wykonywane na podstawie stanu obiektu.  
  
     Przykładem może być próba zapisu w pliku tylko do odczytu. W przypadkach, w których stan obiektu nie zezwala na operację, zgłoś wystąpienie <xref:System.InvalidOperationException> obiektu lub obiekt na podstawie wartości pochodnych tej klasy. Jest to przykład metody, która zgłasza <xref:System.InvalidOperationException> obiekt:  
  
     [!code-csharp[csProgGuideExceptions#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#13)]  
  
- Gdy argument metody powoduje wyjątek.  
  
     W takim przypadku należy przechwycić oryginalny wyjątek i <xref:System.ArgumentException> utworzyć wystąpienie. Oryginalny wyjątek powinien zostać przesłany do konstruktora <xref:System.ArgumentException> jako <xref:System.Exception.InnerException%2A> parametr:  
  
     [!code-csharp[csProgGuideExceptions#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#14)]  
  
 Wyjątki zawierają właściwość o nazwie <xref:System.Exception.StackTrace%2A> . Ten ciąg zawiera nazwę metod w bieżącym stosie wywołań, wraz z nazwą pliku i numerem wiersza, dla których zgłoszono wyjątek dla każdej metody. <xref:System.Exception.StackTrace%2A>Obiekt jest tworzony automatycznie przez środowisko uruchomieniowe języka wspólnego (CLR) z punktu `throw` instrukcji, aby wyjątki musiały zostać zgłoszone od punktu, w którym ma zostać rozpoczęte śledzenie stosu.  
  
 Wszystkie wyjątki zawierają właściwość o nazwie <xref:System.Exception.Message%2A> . Ten ciąg powinien być ustawiony na wyjaśnienie przyczyny wyjątku. Należy pamiętać, że informacje, które są wrażliwe na zabezpieczenia, nie powinny być umieszczane w tekście komunikatu. Oprócz <xref:System.Exception.Message%2A> , <xref:System.ArgumentException> zawiera właściwość o nazwie <xref:System.ArgumentException.ParamName%2A> , która powinna być ustawiona na nazwę argumentu, który spowodował zgłoszenie wyjątku. W przypadku metody ustawiającej właściwość <xref:System.ArgumentException.ParamName%2A> powinna być ustawiona na `value` .  
  
 Metody publiczne i chronione powinny generować wyjątki, gdy nie mogą zakończyć ich zamierzonych funkcji. Zgłoszona Klasa wyjątku powinna być najbardziej szczegółowym dostępnym wyjątkiem, który pasuje do warunków błędu. Te wyjątki powinny być udokumentowane jako część funkcji klasy, a klasy pochodne lub aktualizacje oryginalnej klasy powinny zachować takie samo zachowanie w celu zapewnienia zgodności z poprzednimi wersjami.  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a>Rzeczy, które należy unikać podczas zgłaszania wyjątków  
 Poniższa lista zawiera wskazówki, które należy unikać podczas zgłaszania wyjątków:  
  
- Wyjątków nie należy używać do zmiany przepływu programu w ramach zwykłego wykonania. Wyjątki powinny być używane tylko do raportowania i obsługi warunków błędów.  
  
- Wyjątków nie należy zwracać jako wartości zwracanej lub parametru, a nie do zgłaszania.  
  
- Nie zgłaszaj <xref:System.Exception?displayProperty=nameWithType> , <xref:System.SystemException?displayProperty=nameWithType> , <xref:System.NullReferenceException?displayProperty=nameWithType> lub <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> celowo z własnego kodu źródłowego.  
  
- Nie należy tworzyć wyjątków, które mogą być zgłaszane w trybie debugowania, ale nie w trybie wydania. Aby zidentyfikować błędy czasu wykonywania w fazie opracowywania, należy zamiast tego użyć potwierdzenia debugowania.  
  
## <a name="defining-exception-classes"></a>Definiowanie klas wyjątków  
 Programy mogą zgłosić wstępnie zdefiniowaną klasę wyjątku w <xref:System> przestrzeni nazw (chyba że wcześniej zanotowano) lub utworzyć własne klasy wyjątków, wyprowadzając z <xref:System.Exception> . Klasy pochodne powinny definiować co najmniej cztery konstruktory: jeden konstruktor bez parametrów, taki, który ustawia właściwość Message, a drugi ustawia <xref:System.Exception.Message%2A> <xref:System.Exception.InnerException%2A> właściwości i. Czwarty Konstruktor jest używany do serializacji wyjątku. Nowe klasy wyjątków powinny być możliwe do serializacji. Na przykład:  
  
 [!code-csharp[csProgGuideExceptions#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#15)]  
  
 Nowe właściwości powinny być dodawane do klasy wyjątku tylko wtedy, gdy udostępniane dane są przydatne do rozpoznawania wyjątku. Jeśli do klasy wyjątku pochodnego zostaną dodane nowe właściwości, `ToString()` należy je zastąpić, aby zwracały dodane informacje.  
  
## <a name="c-language-specification"></a>Specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [wyjątki](~/_csharplang/spec/exceptions.md) i [instrukcje throw](~/_csharplang/spec/statements.md#the-throw-statement) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Wyjątki i obsługa wyjątków](./index.md)
- [Hierarchia wyjątków](../../../standard/exceptions/index.md)
- [Obsługa wyjątków](./exception-handling.md)
