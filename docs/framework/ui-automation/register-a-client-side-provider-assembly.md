---
title: Rejestrowanie zestawów dostawcy po stronie klienta
description: Zapoznaj się z przykładem, który pokazuje, jak zarejestrować bibliotekę DLL, która zawiera dostawców automatyzacji interfejsu użytkownika po stronie klienta.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- registering client-side provider assemblies
- client-side provider assemblies, registering
- UI Automation, registering provider assemblies
- provider assemblies, registering
ms.assetid: a03af4d9-2771-43cc-b07b-d468dca23190
ms.openlocfilehash: 1c6f7685b796b544925207a22679e6a4da455844
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250466"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="62a4f-103">Rejestrowanie zestawów dostawcy po stronie klienta</span><span class="sxs-lookup"><span data-stu-id="62a4f-103">Register a Client-Side Provider Assembly</span></span>

> [!NOTE]
> <span data-ttu-id="62a4f-104">Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="62a4f-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="62a4f-105">Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="62a4f-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="62a4f-106">W tym temacie przedstawiono sposób rejestrowania biblioteki DLL zawierającej dostawców automatyzacji interfejsu użytkownika po stronie klienta.</span><span class="sxs-lookup"><span data-stu-id="62a4f-106">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62a4f-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="62a4f-107">Example</span></span>  

 <span data-ttu-id="62a4f-108">Poniższy przykład pokazuje, jak zarejestrować zestaw, który zawiera dostawcę okna konsoli.</span><span class="sxs-lookup"><span data-stu-id="62a4f-108">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="62a4f-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="62a4f-109">See also</span></span>

- [<span data-ttu-id="62a4f-110">Tworzenie dostawcy automatyzacji interfejsu użytkownika po stronie klienta</span><span class="sxs-lookup"><span data-stu-id="62a4f-110">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)
