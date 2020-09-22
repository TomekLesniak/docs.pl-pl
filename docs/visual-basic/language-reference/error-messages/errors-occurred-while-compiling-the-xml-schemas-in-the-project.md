---
title: Wystąpiły błędy podczas kompilowania schematów XML w projekcie
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 17c31301e28c757954e72ba103254f038905671f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874355"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Wystąpiły błędy podczas kompilowania schematów XML w projekcie

Wystąpiły błędy podczas kompilowania schematów XML w projekcie. Z tego powodu funkcja IntelliSense języka XML jest niedostępna.  
  
 Wystąpił błąd w schemacie definicji schematu XML (XSD) zawartym w projekcie. Ten błąd występuje po dodaniu pliku schematu XSD (XSD), który powoduje konflikt z istniejącym zestawem schematu XSD dla projektu.  
  
 **Identyfikator błędu:** BC36810  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Kliknij dwukrotnie ostrzeżenie w oknie **Lista błędów** . Visual Basic przejdzie do lokalizacji w pliku XSD, który jest źródłem ostrzeżenia. Popraw błąd w schemacie XSD.  
  
- Upewnij się, że w projekcie są zawarte wszystkie wymagane pliki schematu XSD (XSD). Może być konieczne kliknięcie przycisku **Pokaż wszystkie pliki** w menu **projekt** , aby wyświetlić pliki XSD w **Eksplorator rozwiązań**. Kliknij prawym przyciskiem myszy plik XSD, a następnie kliknij pozycję **Dołącz w projekcie** , aby dołączyć plik do projektu.  
  
- Jeśli używasz Kreatora XML do schematu, ten błąd może wystąpić w przypadku wywnioskowania schematów więcej niż jeden raz z tego samego źródła. W takim przypadku można usunąć istniejące pliki schematu XSD z projektu, dodać nowe XML do szablonu elementu schematu, a następnie udostępnić kreatora XML do schematu wszystkim odpowiednim źródłom XML dla projektu.  
  
- Jeśli żaden błąd nie zostanie zidentyfikowany w schemacie XSD, kompilator XML może nie mieć wystarczającej ilości informacji, aby przedstawić szczegółowy komunikat o błędzie. Jeśli masz pewność, że przestrzenie nazw XML dla plików XSD zawartych w projekcie są zgodne z przestrzeniami nazw XML określonymi dla zestawu schematu XML w programie Visual Studio, możesz uzyskać bardziej szczegółowe informacje o błędzie.  
  
## <a name="see-also"></a>Zobacz też

- [Okno Lista błędów](/visualstudio/ide/reference/error-list-window)
- [XML](../../programming-guide/language-features/xml/index.md)
