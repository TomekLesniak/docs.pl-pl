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
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="8aa43-104">Tworzenie dostawcy automatyzacji interfejsu użytkownika po stronie klienta</span><span class="sxs-lookup"><span data-stu-id="8aa43-104">Create a Client-Side UI Automation Provider</span></span>

> [!NOTE]
> <span data-ttu-id="8aa43-105">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="8aa43-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8aa43-106">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="8aa43-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8aa43-107">Ten temat zawiera przykładowy kod pokazujący sposób implementacji dostawcy automatyzacji interfejsu użytkownika po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="8aa43-107">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aa43-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="8aa43-108">Example</span></span>  

 <span data-ttu-id="8aa43-109">Poniższy przykładowy kod można utworzyć w bibliotece dołączanej dynamicznie (DLL), która implementuje bardzo prostego dostawcę po stronie klienta dla okna konsoli.</span><span class="sxs-lookup"><span data-stu-id="8aa43-109">The following example code can be built into a dynamic-link library (DLL) that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="8aa43-110">Kod nie ma żadnych użytecznych funkcji, ale ma na celu przedstawienie podstawowych kroków konfiguracji zestawu dostawcy, który może być zarejestrowany przez aplikację klienta automatyzacji interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8aa43-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="8aa43-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8aa43-111">See also</span></span>

- [<span data-ttu-id="8aa43-112">Przegląd dostawców automatyzacji interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="8aa43-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="8aa43-113">Rejestrowanie zestawów dostawcy po stronie klienta</span><span class="sxs-lookup"><span data-stu-id="8aa43-113">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
