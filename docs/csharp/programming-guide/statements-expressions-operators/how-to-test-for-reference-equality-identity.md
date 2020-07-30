---
title: Jak przetestować równość odwołań (tożsamość) — Przewodnik programowania w języku C#
description: Dowiedz się, jak przetestować równość odwołań (tożsamość). Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: fece0fbc0179f5707e7f3fcd62371b8dde84eb6a
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381388"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a>Testowanie równości odwołań (tożsamość) (Przewodnik programowania w języku C#)
Nie trzeba implementować żadnej logiki niestandardowej w celu obsługi porównania równości odwołań w typach. Ta funkcja jest dostępna dla wszystkich typów przez metodę statyczną <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> .  
  
 Poniższy przykład pokazuje, jak określić, czy dwie zmienne mają *równość odwołania*, co oznacza, że odwołują się do tego samego obiektu w pamięci.  
  
 W przykładzie pokazano również, dlaczego <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> zawsze są zwracane `false` dla typów wartości i dlaczego nie należy używać <xref:System.Object.ReferenceEquals%2A> do określania równości ciągów.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[csProgGuideObjects#90](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#90)]  
  
 Implementacja `Equals` w <xref:System.Object?displayProperty=nameWithType> uniwersalnej klasie bazowej również wykonuje kontrolę równości odwołań, ale nie jest to zalecane, ponieważ jeśli klasa ma przesłonić metodę, wyniki mogą nie być oczekiwane. Ta sama wartość dotyczy `==` `!=` operatorów i. Gdy są one wykonywane na typach referencyjnych, domyślne zachowanie `==` i `!=` ma na celu wykonywanie kontroli równości odwołań. Jednak klasy pochodne mogą przeciążać operator, aby wykonać kontrolę równości wartości. Aby zminimalizować prawdopodobieństwo wystąpienia błędu, najlepiej jest zawsze używać, gdy trzeba <xref:System.Object.ReferenceEquals%2A> określić, czy dwa obiekty mają równość odwołania.  
  
 Stałe ciągi w tym samym zestawie są zawsze Interni przez środowisko uruchomieniowe. Oznacza to, że jest obsługiwane tylko jedno wystąpienie każdego unikatowego ciągu literału. Jednak środowisko uruchomieniowe nie gwarantuje, że ciągi utworzone w czasie wykonywania są InterNIC, ani nie gwarantujemy, że dwie równe ciągi stałe w różnych zestawach są InterNIC.  
  
## <a name="see-also"></a>Zobacz też

- [Porównania równości](./equality-comparisons.md)
