---
title: Rozpoznanie późnego wiązania; mogą wystąpić błędy podczas wykonywania
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 1c7b352c7bd61216ecce9901585945e740428ee3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873859"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Rozpoznanie późnego wiązania; mogą wystąpić błędy podczas wykonywania

Obiekt jest przypisany do zmiennej zadeklarowanej jako [Typ danych obiektu](../data-types/object-data-type.md).  
  
 Po zadeklarowaniu zmiennej jako `Object` , kompilator musi wykonać *późne wiązanie*, co powoduje dodatkowe operacje w czasie wykonywania. Udostępnia również aplikacji potencjalne błędy w czasie wykonywania. Na przykład, Jeśli przypiszesz <xref:System.Windows.Forms.Form> do `Object` zmiennej, a następnie spróbujesz uzyskać dostęp do <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> właściwości, środowisko uruchomieniowe zgłosi, <xref:System.MemberAccessException> ponieważ Klasa nie <xref:System.Windows.Forms.Form> uwidacznia `NameTable` właściwości.  
  
 W przypadku deklarowania zmiennej jako określonego typu kompilator może wykonać *wczesne powiązanie* w czasie kompilacji. Powoduje to zwiększenie wydajności, kontrolowany dostęp do elementów członkowskich określonego typu i lepszą czytelność kodu.  
  
 Domyślnie ten komunikat jest ostrzeżeniem. Aby uzyskać informacje na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędy, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identyfikator błędu:** BC42017  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Jeśli to możliwe, zadeklaruj zmienną jako określonego typu.  
  
## <a name="see-also"></a>Zobacz też

- [Wczesne i późne powiązania](../../programming-guide/language-features/early-late-binding/index.md)
- [Deklaracja zmiennej obiektu](../../programming-guide/language-features/variables/object-variable-declaration.md)
