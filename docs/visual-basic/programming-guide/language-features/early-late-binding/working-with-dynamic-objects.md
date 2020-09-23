---
title: Praca z obiektami dynamicznymi
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 45f8b5c327d40f93b59c2115c75b3b7d385f5a8d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057926"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Praca z obiektami dynamicznymi (Visual Basic)

Obiekty dynamiczne zapewniają inny sposób, inny niż `Object` Typ, do późnego powiązania z obiektem w czasie wykonywania. Obiekt dynamiczny ujawnia składowe, takie jak właściwości i metody w czasie wykonywania, przy użyciu interfejsów dynamicznych, które są zdefiniowane w <xref:System.Dynamic> przestrzeni nazw. Klas w <xref:System.Dynamic> przestrzeni nazw można użyć do tworzenia obiektów, które współpracują ze strukturami danych, które nie pasują do statycznego typu lub formatu. Można również używać obiektów dynamicznych, które są zdefiniowane w językach dynamicznych, takich jak IronPython i IronRuby. Przykłady pokazujące sposób tworzenia obiektów dynamicznych lub korzystania z obiektu dynamicznego zdefiniowanego w języku dynamicznym można znaleźć w temacie [Przewodnik: Tworzenie i używanie obiektów dynamicznych](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject> lub <xref:System.Dynamic.ExpandoObject> .  
  
 Visual Basic powiązania z obiektami z poziomu środowiska uruchomieniowego języka dynamicznego i języków dynamicznych, takich jak IronPython i IronRuby, za pomocą <xref:System.Dynamic.IDynamicMetaObjectProvider> interfejsu. Przykładami klas, które implementują `IDynamicMetaObjectProvider` interfejs, <xref:System.Dynamic.DynamicObject> są <xref:System.Dynamic.ExpandoObject> klasy i.  
  
 W przypadku wywołania z późnym wiązaniem do obiektu, który implementuje `IDynamicMetaObjectProvider` interfejs, Visual Basic tworzy powiązanie z obiektem dynamicznym przy użyciu tego interfejsu. W przypadku wywołania z późnym wiązaniem do obiektu, który nie implementuje `IDynamicMetaObjectProvider` interfejsu, lub jeśli wywołanie `IDynamicMetaObjectProvider` interfejsu zakończy się niepowodzeniem, Visual Basic powiązania z obiektem przy użyciu możliwości późnego wiązania środowiska uruchomieniowego Visual Basic.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Przewodnik: Tworzenie obiektów dynamicznych i korzystanie z nich](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Wczesne i późne powiązania](index.md)
