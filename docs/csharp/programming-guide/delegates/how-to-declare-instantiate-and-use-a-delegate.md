---
title: Jak zadeklarować, utworzyć wystąpienie i użyć przewodnika programowania delegata w języku C#
description: Dowiedz się, jak zadeklarować delegata, utworzyć jego wystąpienie i użyć go. Zobacz przykłady, które obejmują Języki C# 1,0, 2,0 i 3,0 i nowsze.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: b741b3bc9c03faaa5fa2c01bd8f70d4be9b099c2
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063669"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a>Sposób deklarowania, tworzenia wystąpienia i używania delegata (Przewodnik programowania w języku C#)
W języku C# 1,0 i nowszych można zadeklarować delegatów, jak pokazano w poniższym przykładzie.  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 Język C# 2,0 zapewnia prostszy sposób pisania poprzedniej deklaracji, jak pokazano w poniższym przykładzie.  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 W języku C# 2,0 i nowszych jest również możliwe użycie anonimowej metody do deklarowania i zainicjowania [delegata](../../language-reference/builtin-types/reference-types.md), jak pokazano w poniższym przykładzie.  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 W języku C# 3,0 i nowszych Delegaty mogą być również deklarowane i tworzone przy użyciu wyrażenia lambda, jak pokazano w poniższym przykładzie.  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 Aby uzyskać więcej informacji, zobacz [wyrażenia lambda](../../language-reference/operators/lambda-expressions.md).  
  
 Poniższy przykład ilustruje deklarowanie, Tworzenie wystąpień i Używanie delegata. `BookDB`Klasa hermetyzuje bazę danych księgarni, która obsługuje bazę danych książek. Udostępnia ona metodę, `ProcessPaperbackBooks` która znajduje wszystkie książki drukowanego podręcznika w bazie danych i wywołuje delegata dla każdego z nich. `delegate`Typ, który jest używany, ma nazwę `ProcessBookDelegate` . `Test`Klasa używa tej klasy do drukowania tytułów i średniej ceny książek drukowanego podręcznika.  
  
 Użycie delegatów promuje dobre rozdzielenie funkcjonalności między bazą danych księgarni i kodem klienta. Kod klienta nie ma informacji o tym, w jaki sposób są przechowywane książki lub jak kod księgarni znajduje książki drukowanego podręcznika. Kod księgarni nie ma informacji o tym, jakie przetwarzanie jest wykonywane w książkach drukowanego podręcznika po ich znalezieniu.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
  
- Deklarowanie delegata.  
  
     Poniższa instrukcja deklaruje nowy typ delegata.  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     Każdy typ delegata zawiera informacje o liczbie i typach argumentów oraz typ zwracanej wartości metod, które mogą być hermetyzowane. Zawsze, gdy wymagany jest nowy zestaw typów argumentów lub typ wartości zwracanej, musi zostać zadeklarowany nowy typ delegata.  
  
- Utworzenie wystąpienia obiektu delegowanego.  
  
     Po zadeklarowaniu typu delegata należy utworzyć obiekt delegata i skojarzyć go z określoną metodą. W poprzednim przykładzie należy to zrobić, przekazując `PrintTitle` metodę do `ProcessPaperbackBooks` metody, jak w poniższym przykładzie:  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     Spowoduje to utworzenie nowego obiektu delegata skojarzonego z metodą [statyczną](../../language-reference/keywords/static.md) `Test.PrintTitle` . Podobnie Metoda niestatyczna `AddBookToTotal` w obiekcie `totaller` jest przenoszona jak w poniższym przykładzie:  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     W obu przypadkach nowy obiekt delegata jest przenoszona do `ProcessPaperbackBooks` metody.  
  
     Po utworzeniu delegata Metoda jest skojarzona z nigdy zmianami; obiekty delegatów są niezmienne.  
  
- Wywoływanie delegata.  
  
     Po utworzeniu obiektu delegowanego obiekt delegata jest zwykle przenoszona do innego kodu, który wywoła delegata. Obiekt delegata jest wywoływany przy użyciu nazwy obiektu delegata, a następnie argumentów ujętych w nawiasy, które mają być przekazane do obiektu delegowanego. Poniżej znajduje się przykład wywołania delegata:  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     Delegat może być wywołany synchronicznie, jak w tym przykładzie lub asynchronicznie przy użyciu `BeginInvoke` metod i `EndInvoke` .  
  
## <a name="see-also"></a>Zobacz także

- [Przewodnik programowania w języku C#](../index.md)
- [Zdarzenia](../events/index.md)
- [Delegaty](./index.md)
