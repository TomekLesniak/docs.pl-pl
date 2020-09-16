---
title: 'Instrukcje: Wywoływanie interfejsów API systemu Windows'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 863986e94855e02e9fd04685f7dc3e8e7f7b1cc3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548068"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Porady: wywoływanie Windows API (Visual Basic)
Ten przykład definiuje i wywołuje `MessageBox` funkcję w user32.dll a następnie przekazuje do niej ciąg.  
  
## <a name="example"></a>Przykład  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>Kompiluj kod  
 Ten przykład wymaga:  
  
- Odwołanie do <xref:System> przestrzeni nazw.  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Następujące warunki mogą spowodować wyjątek:  
  
- Metoda nie jest statyczna, jest abstrakcyjna lub została wcześniej zdefiniowana. Typ nadrzędny jest interfejsem lub długość *nazwy* lub *nazwa_pliku_dll* ma wartość zero. (<xref:System.ArgumentException>)  
  
- *Nazwa* lub *nazwa_pliku_dll* ma wartość `Nothing` . (<xref:System.ArgumentNullException>)  
  
- Typ zawierający został wcześniej utworzony przy użyciu `CreateType` . (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Zobacz także

- [Bliższe spojrzenie na wywołanie platformy](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Przykłady wywołań platformy](../../../framework/interop/platform-invoke-examples.md)
- [Wykorzystywanie niezarządzanych funkcji DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Definiowanie metody przy użyciu emisji odbicia](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Przewodnik: Wywoływanie interfejsów API systemu Windows](walkthrough-calling-windows-apis.md)
- [Międzyoperacyjność modelu COM](index.md)
