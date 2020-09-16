---
title: Udostępnianie składników .NET do modelu COM
description: Uwidocznij składniki platformy .NET w modelu COM. Kwalifikowanie typów .NET do międzyoperacyjności. Zastosuj atrybuty międzyoperacyjności. Pakowanie zestawu dla modelu COM. Korzystaj z typu zarządzanego z modelu COM.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
ms.openlocfilehash: dc808f3e8d6bd89ba979d43e5b4ec9d787bd09b1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545262"
---
# <a name="exposing-net-components-to-com"></a><span data-ttu-id="6bc03-107">Udostępnianie składników .NET do modelu COM</span><span class="sxs-lookup"><span data-stu-id="6bc03-107">Exposing .NET components to COM</span></span>

<span data-ttu-id="6bc03-108">Pisanie typu .NET i używanie tego typu z kodu niezarządzanego to odrębne działania dla deweloperów.</span><span class="sxs-lookup"><span data-stu-id="6bc03-108">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="6bc03-109">W tej sekcji opisano kilka wskazówek dotyczących pisania kodu zarządzanego, który współdziała z klientami COM:</span><span class="sxs-lookup"><span data-stu-id="6bc03-109">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>

- <span data-ttu-id="6bc03-110">[Kwalifikowanie typów .NET do międzyoperacyjności](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="6bc03-110">[Qualifying .NET types for interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

     <span data-ttu-id="6bc03-111">Wszystkie typy zarządzane, metody, właściwości, pola i zdarzenia, które mają zostać ujawnione w modelu COM, muszą być publiczne.</span><span class="sxs-lookup"><span data-stu-id="6bc03-111">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="6bc03-112">Typy muszą mieć publiczny Konstruktor bez parametrów, który jest jedynym konstruktorem, który może być wywoływany przez COM.</span><span class="sxs-lookup"><span data-stu-id="6bc03-112">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>

- <span data-ttu-id="6bc03-113">[Stosowanie atrybutów międzyoperacyjnych](../../standard/native-interop/apply-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6bc03-113">[Applying interop attributes](../../standard/native-interop/apply-interop-attributes.md).</span></span>

     <span data-ttu-id="6bc03-114">Atrybuty niestandardowe w kodzie zarządzanym mogą wzmocnić współdziałanie składnika.</span><span class="sxs-lookup"><span data-stu-id="6bc03-114">Custom attributes within managed code can enhance the interoperability of a component.</span></span>

- <span data-ttu-id="6bc03-115">[Pakowanie zestawu dla modelu COM](packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="6bc03-115">[Packaging an assembly for COM](packaging-an-assembly-for-com.md).</span></span>

     <span data-ttu-id="6bc03-116">Deweloperzy COM mogą wymagać podsumowania kroków związanych z odwołującymi się i wdrażaniem zestawów.</span><span class="sxs-lookup"><span data-stu-id="6bc03-116">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>

 <span data-ttu-id="6bc03-117">Ponadto w tej sekcji przedstawiono zadania związane z zużywaniem typu zarządzanego z klienta COM.</span><span class="sxs-lookup"><span data-stu-id="6bc03-117">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>

## <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="6bc03-118">Aby użyć typu zarządzanego z modelu COM</span><span class="sxs-lookup"><span data-stu-id="6bc03-118">To consume a managed type from COM</span></span>

1. <span data-ttu-id="6bc03-119">[Zarejestruj zestawy przy użyciu modelu COM](registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="6bc03-119">[Register assemblies with COM](registering-assemblies-with-com.md).</span></span>

     <span data-ttu-id="6bc03-120">Typy w zestawie (i biblioteki typów) muszą być zarejestrowane w czasie projektowania.</span><span class="sxs-lookup"><span data-stu-id="6bc03-120">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="6bc03-121">Jeśli Instalator nie rejestruje zestawu, poinstruuj deweloperów COM, aby korzystali z Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="6bc03-121">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>

2. <span data-ttu-id="6bc03-122">[Odwołuj się do typów .NET z modelu COM](how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="6bc03-122">[Reference .NET types from COM](how-to-reference-net-types-from-com.md).</span></span>

     <span data-ttu-id="6bc03-123">Deweloperzy COM mogą odwoływać się do typów w zestawie przy użyciu tych samych narzędzi i technik, których używają dzisiaj.</span><span class="sxs-lookup"><span data-stu-id="6bc03-123">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>

3. <span data-ttu-id="6bc03-124">[Wywoływanie obiektu .NET](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6bc03-124">[Call a .NET object](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>

     <span data-ttu-id="6bc03-125">Deweloperzy COM mogą wywoływanie metod w obiekcie .NET w taki sam sposób, jak wywoływanie metod dla dowolnego typu niezarządzanego.</span><span class="sxs-lookup"><span data-stu-id="6bc03-125">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="6bc03-126">Na przykład interfejs API funkcji **COCREATEINSTANCE** com aktywuje obiekty .NET.</span><span class="sxs-lookup"><span data-stu-id="6bc03-126">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>

4. <span data-ttu-id="6bc03-127">[Wdróż aplikację na potrzeby dostępu do modelu COM](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6bc03-127">[Deploy an application for COM access](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>

     <span data-ttu-id="6bc03-128">Zestaw o silnej nazwie można zainstalować w globalnej pamięci podręcznej zestawów i wymaga podpisu od jego wydawcy.</span><span class="sxs-lookup"><span data-stu-id="6bc03-128">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="6bc03-129">Zestawy, które nie mają silnej nazwy, muszą być zainstalowane w katalogu aplikacji klienta.</span><span class="sxs-lookup"><span data-stu-id="6bc03-129">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bc03-130">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6bc03-130">See also</span></span>

- [<span data-ttu-id="6bc03-131">Współdziałanie z kodem niezarządzanym</span><span class="sxs-lookup"><span data-stu-id="6bc03-131">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="6bc03-132">Przykład usługi międzyoperacyjnej modelu COM: Klient modelu COM i serwer .NET</span><span class="sxs-lookup"><span data-stu-id="6bc03-132">COM Interop Sample: COM Client and .NET Server</span></span>](com-interop-sample-com-client-and-net-server.md)
