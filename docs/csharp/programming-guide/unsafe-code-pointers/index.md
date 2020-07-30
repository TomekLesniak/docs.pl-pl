---
title: Niebezpieczny kod i wskaźniki — Przewodnik programowania w języku C#
Description: Poznaj niebezpieczny kod i wskaźniki. Język C# nie obsługuje wskaźników, ale można zdefiniować niebezpieczny kontekst, w którym wskaźniki mogą być używane ze słowem kluczowym "UNSAFE".
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 5684a97ed6f7b6632d8fe3d52747d9187c4b8cbc
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381778"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a>Niebezpieczny kod i wskaźniki (Przewodnik programowania w języku C#)

Aby zachować bezpieczeństwo typu i zabezpieczenia, język C# nie obsługuje domyślnie arytmetycznego wskaźnika. Jednak za pomocą słowa kluczowego [UNSAFE](../../language-reference/keywords/unsafe.md) można zdefiniować niebezpieczny kontekst, w którym można używać wskaźników. Aby uzyskać więcej informacji na temat wskaźników, zobacz [typy wskaźnika](pointer-types.md).  
  
> [!NOTE]
> W środowisku uruchomieniowym języka wspólnego (CLR) kod niebezpieczny jest określany jako kod niemożliwy do zweryfikowania. Kod niebezpieczny w języku C# nie musi być niebezpieczny; jest to tylko kod, którego bezpieczeństwo nie może być zweryfikowane przez środowisko CLR. W związku z tym środowisko CLR wykona tylko niebezpieczny kod, jeśli znajduje się w w pełni zaufanym zestawie. Jeśli używasz niebezpiecznego kodu, jest odpowiedzialny za upewnienie się, że Twój kod nie wprowadza zagrożeń bezpieczeństwa lub błędy wskaźników.  
  
## <a name="unsafe-code-overview"></a>Przegląd niebezpiecznego kodu

Kod niebezpieczny ma następujące właściwości:

- Metody, typy i bloki kodu można definiować jako niebezpieczne.

- W niektórych przypadkach niebezpieczny kod może zwiększyć wydajność aplikacji przez usunięcie kontroli granic tablicy.

- Kod niebezpieczny jest wymagany po wywołaniu funkcji natywnych, które wymagają wskaźników.

- Użycie niebezpiecznego kodu wprowadza zagrożenia bezpieczeństwa i stabilności.

- Kod, który zawiera niebezpieczne bloki, musi być skompilowany przy użyciu opcji [niebezpiecznego](../../language-reference/compiler-options/unsafe-compiler-option.md) kompilatora.
  
## <a name="related-sections"></a>Sekcje pokrewne

Aby uzyskać więcej informacji, zobacz:

- [Typy wskaźnika](pointer-types.md)

- [Bufory o ustalonym rozmiarze](fixed-size-buffers.md)

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz temat [niebezpieczny kod](~/_csharplang/spec/unsafe-code.md) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [niebezpieczne](../../language-reference/keywords/unsafe.md)
