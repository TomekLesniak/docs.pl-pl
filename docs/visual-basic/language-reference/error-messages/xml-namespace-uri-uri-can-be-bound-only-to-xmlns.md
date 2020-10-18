---
title: Identyfikator URI „<uri>” przestrzeni nazw XML może być powiązany tylko z elementem „xmlns”
ms.date: 07/20/2015
f1_keywords:
- bc31183
- vbc31183
helpviewer_keywords:
- BC31183
ms.assetid: 0ab1dbce-8397-4959-b2cd-f58798b051a0
ms.openlocfilehash: 1aec6ac0a354bfe7e0378a2e46a70a7161bf6d36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163249"
---
# <a name="bc31183-xml-namespace-uri-httpwwww3orgxml1998namespace-can-be-bound-only-to-xmlns"></a>BC31183: identyfikator URI przestrzeni nazw XML `http://www.w3.org/XML/1998/namespace` ; może być powiązany tylko z elementem "xmlns"

Identyfikator URI `http://www.w3.org/XML/1998/namespace` jest używany w deklaracji przestrzeni nazw XML. Ten identyfikator URI jest zarezerwowaną przestrzenią nazw i nie można go uwzględnić w deklaracji przestrzeni nazw XML.

 **Identyfikator błędu:** BC31183

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

Usuń deklarację przestrzeni nazw XML lub Zastąp identyfikator URI `http://www.w3.org/XML/1998/namespace` prawidłowym identyfikatorem URI przestrzeni nazw.

## <a name="see-also"></a>Zobacz też

- [Imports — Instrukcja (przestrzeń nazw XML)](../statements/imports-statement-xml-namespace.md)
- [Literały XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
