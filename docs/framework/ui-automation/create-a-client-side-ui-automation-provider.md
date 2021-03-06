---
title: Tworzenie dostawcy automatyzacji interfejsu użytkownika po stronie klienta
description: Zapoznaj się z przykładem tworzenia dostawcy automatyzacji interfejsu użytkownika po stronie klienta. Przykład implementuje prostego dostawcę po stronie klienta dla okna konsoli.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: 17a6deca2efc67d1409e89f7accf7a3b89a27807
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276545"
---
# <a name="create-a-client-side-ui-automation-provider"></a>Tworzenie dostawcy automatyzacji interfejsu użytkownika po stronie klienta

> [!NOTE]
> Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw. Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).  
  
 Ten temat zawiera przykładowy kod pokazujący sposób implementacji dostawcy automatyzacji interfejsu użytkownika po stronie klienta.  
  
## <a name="example"></a>Przykład  

 Poniższy przykładowy kod można utworzyć w bibliotece dołączanej dynamicznie (DLL), która implementuje bardzo prostego dostawcę po stronie klienta dla okna konsoli. Kod nie ma żadnych użytecznych funkcji, ale ma na celu przedstawienie podstawowych kroków konfiguracji zestawu dostawcy, który może być zarejestrowany przez aplikację klienta automatyzacji interfejsu użytkownika.  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a>Zobacz też

- [Przegląd dostawców automatyzacji interfejsu użytkownika](ui-automation-providers-overview.md)
- [Rejestrowanie zestawów dostawcy po stronie klienta](register-a-client-side-provider-assembly.md)
