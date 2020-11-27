---
title: 'Instrukcje: Odwołania do typów .NET z modelu COM'
description: Odwołuj się do typów .NET z modelu COM. Klienci VB mogą wyświetlać obiekt .NET w przeglądarce obiektów, ale klienci C++ muszą odwoływać się do pliku TLB przy użyciu \# dyrektywy import.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: 4e6e9f13364241517167c341a04883a199e9d6c2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267029"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="0af47-104">Instrukcje: Odwołania do typów .NET z modelu COM</span><span class="sxs-lookup"><span data-stu-id="0af47-104">How to: Reference .NET Types from COM</span></span>

<span data-ttu-id="0af47-105">Z punktu widzenia kodu klienta i serwera różnice między modelem COM i .NET Framework są bardzo niewidoczne.</span><span class="sxs-lookup"><span data-stu-id="0af47-105">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="0af47-106">Klienci programu Microsoft Visual Basic mogą wyświetlać obiekt .NET w przeglądarce obiektów, która udostępnia metody obiektu i składnię, właściwości i pola dokładnie tak, jakby były dowolnym innym obiektem COM.</span><span class="sxs-lookup"><span data-stu-id="0af47-106">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="0af47-107">Proces importowania biblioteki typów jest nieco bardziej skomplikowany dla klientów C++, chociaż te same narzędzia są używane do eksportowania metadanych do biblioteki typów COM.</span><span class="sxs-lookup"><span data-stu-id="0af47-107">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="0af47-108">Aby odwołać się do elementów członkowskich obiektu platformy .NET z niezarządzanego klienta C++, należy odwołać się do pliku TLB (utworzonego za pomocą Tlbexp.exe) za pomocą dyrektywy **#import** .</span><span class="sxs-lookup"><span data-stu-id="0af47-108">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="0af47-109">W przypadku odwoływania się do biblioteki typów z C++ należy określić opcję **raw_interfaces_only** lub zaimportować definicje w bibliotece klas bazowych, mscorlib. tlb.</span><span class="sxs-lookup"><span data-stu-id="0af47-109">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="0af47-110">Aby zaimportować bibliotekę</span><span class="sxs-lookup"><span data-stu-id="0af47-110">To import a library</span></span>  
  
- <span data-ttu-id="0af47-111">W dyrektywie **#import** określ opcję **raw_interfaces_only** .</span><span class="sxs-lookup"><span data-stu-id="0af47-111">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="0af47-112">Przykład:</span><span class="sxs-lookup"><span data-stu-id="0af47-112">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="0af47-113">-lub-</span><span class="sxs-lookup"><span data-stu-id="0af47-113">-or-</span></span>  
  
- <span data-ttu-id="0af47-114">Uwzględnij #import dyrektywę dla biblioteki mscorlib. tlb.</span><span class="sxs-lookup"><span data-stu-id="0af47-114">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="0af47-115">Przykład:</span><span class="sxs-lookup"><span data-stu-id="0af47-115">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0af47-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0af47-116">See also</span></span>

- [<span data-ttu-id="0af47-117">Udostępnianie składników .NET Framework modelowi COM</span><span class="sxs-lookup"><span data-stu-id="0af47-117">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="0af47-118">Rejestrowanie zestawów do użycia z modelem COM</span><span class="sxs-lookup"><span data-stu-id="0af47-118">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="0af47-119">[Wywołanie obiektu .NET](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0af47-119">[Calling a .NET Object](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="0af47-120">[Wdrażanie aplikacji na potrzeby dostępu do modelu COM](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0af47-120">[Deploying an Application for COM Access](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>
