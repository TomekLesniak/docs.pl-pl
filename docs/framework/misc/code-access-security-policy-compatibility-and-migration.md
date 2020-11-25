---
title: Zgodność i migracja zasad zabezpieczenia dostępu kodu
description: Zapoznaj się z podsumowaniem i zobacz linki dotyczące zgodności i migracji zasad zabezpieczeń dostępu kodu w .NET Framework 4.
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: 389976556175c0b6b300e75d01327d91f94f0db9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733389"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="7a2de-103">Zgodność i migracja zasad zabezpieczenia dostępu kodu</span><span class="sxs-lookup"><span data-stu-id="7a2de-103">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="7a2de-104">Część zasad zabezpieczeń dostępu kodu (CAS) była przestarzała w .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7a2de-104">The policy portion of code access security (CAS) has been made obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="7a2de-105">W związku z tym mogą wystąpić ostrzeżenia kompilacji i wyjątki czasu wykonywania w przypadku wywołania przestarzałych typów zasad i elementów członkowskich [jawnie](#explicit_use) lub [niejawnie](#implicit_use) (za pomocą innych typów i elementów członkowskich).</span><span class="sxs-lookup"><span data-stu-id="7a2de-105">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="7a2de-106">Ostrzeżenia i błędy można uniknąć:</span><span class="sxs-lookup"><span data-stu-id="7a2de-106">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="7a2de-107">[Migrowanie](#migration) do .NET Framework 4 zamienników dla przestarzałych wywołań.</span><span class="sxs-lookup"><span data-stu-id="7a2de-107">[Migrating](#migration) to the .NET Framework 4 replacements for the obsolete calls.</span></span>

   <span data-ttu-id="7a2de-108">\- oraz</span><span class="sxs-lookup"><span data-stu-id="7a2de-108">\- or -</span></span>

- <span data-ttu-id="7a2de-109">Korzystanie z [ \<NetFx40_LegacySecurityPolicy> elementu konfiguracji](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) w celu wyboru zgodności ze starszymi zasadami CAS.</span><span class="sxs-lookup"><span data-stu-id="7a2de-109">Using the [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="7a2de-110">Ten temat zawiera następujące sekcje:</span><span class="sxs-lookup"><span data-stu-id="7a2de-110">This topic contains the following sections:</span></span>

- [<span data-ttu-id="7a2de-111">Jawne użycie</span><span class="sxs-lookup"><span data-stu-id="7a2de-111">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="7a2de-112">Niejawne użycie</span><span class="sxs-lookup"><span data-stu-id="7a2de-112">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="7a2de-113">Błędy i ostrzeżenia</span><span class="sxs-lookup"><span data-stu-id="7a2de-113">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="7a2de-114">Migracja: zastępowanie dla przestarzałych wywołań</span><span class="sxs-lookup"><span data-stu-id="7a2de-114">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="7a2de-115">Zgodność: korzystanie z opcji starszej wersji zasad CAS</span><span class="sxs-lookup"><span data-stu-id="7a2de-115">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="7a2de-116">Jawne użycie</span><span class="sxs-lookup"><span data-stu-id="7a2de-116">Explicit Use</span></span>

<span data-ttu-id="7a2de-117">Elementy członkowskie, które bezpośrednio manipulują zasadami zabezpieczeń lub wymagają zasad CAS do piaskownicy, są przestarzałe i domyślnie generują błędy.</span><span class="sxs-lookup"><span data-stu-id="7a2de-117">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="7a2de-118">Przykłady są następujące:</span><span class="sxs-lookup"><span data-stu-id="7a2de-118">Examples of these are:</span></span>

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a><span data-ttu-id="7a2de-119">Niejawne użycie</span><span class="sxs-lookup"><span data-stu-id="7a2de-119">Implicit Use</span></span>

<span data-ttu-id="7a2de-120">Niektóre przeciążenia ładowania zestawów generują błędy ze względu na niejawne użycie zasad CAS.</span><span class="sxs-lookup"><span data-stu-id="7a2de-120">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="7a2de-121">Te przeciążenia mają <xref:System.Security.Policy.Evidence> parametr, który jest używany do rozpoznawania zasad CAS i zapewniają zestaw uprawnień dla zestawu.</span><span class="sxs-lookup"><span data-stu-id="7a2de-121">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="7a2de-122">Poniżej przedstawiono kilka przykładów.</span><span class="sxs-lookup"><span data-stu-id="7a2de-122">Here are some examples.</span></span> <span data-ttu-id="7a2de-123">Przestarzałe przeciążenia to te, które przyjmują <xref:System.Security.Policy.Evidence> jako parametr:</span><span class="sxs-lookup"><span data-stu-id="7a2de-123">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a><span data-ttu-id="7a2de-124">Błędy i ostrzeżenia</span><span class="sxs-lookup"><span data-stu-id="7a2de-124">Errors and Warnings</span></span>

<span data-ttu-id="7a2de-125">Przestarzałe typy i elementy członkowskie generują następujące komunikaty o błędach, gdy są używane.</span><span class="sxs-lookup"><span data-stu-id="7a2de-125">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="7a2de-126">Należy pamiętać, że <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> sam typ nie jest przestarzały.</span><span class="sxs-lookup"><span data-stu-id="7a2de-126">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="7a2de-127">Ostrzeżenie czasu kompilacji:</span><span class="sxs-lookup"><span data-stu-id="7a2de-127">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="7a2de-128">Wyjątek czasu wykonywania:</span><span class="sxs-lookup"><span data-stu-id="7a2de-128">Run-time exception:</span></span>

<span data-ttu-id="7a2de-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="7a2de-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="7a2de-130">Migracja: zastępowanie dla przestarzałych wywołań</span><span class="sxs-lookup"><span data-stu-id="7a2de-130">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="7a2de-131">Określanie poziomu zaufania zestawu</span><span class="sxs-lookup"><span data-stu-id="7a2de-131">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="7a2de-132">Zasady urzędów certyfikacji są często używane do określania uprawnień do zestawu lub poziomu zaufania domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7a2de-132">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="7a2de-133">.NET Framework 4 uwidacznia następujące przydatne właściwości, które nie muszą rozwiązywać zasad zabezpieczeń:</span><span class="sxs-lookup"><span data-stu-id="7a2de-133">The .NET Framework 4 exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="7a2de-134">Tryb piaskownicy domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="7a2de-134">Application Domain Sandboxing</span></span>

<span data-ttu-id="7a2de-135"><xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>Metoda ta jest zwykle używana do wypełniania zestawów w domenie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7a2de-135">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="7a2de-136">.NET Framework 4 uwidacznia składowe, które nie muszą być używane <xref:System.Security.Policy.PolicyLevel> do tego celu.</span><span class="sxs-lookup"><span data-stu-id="7a2de-136">The .NET Framework 4 exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="7a2de-137">Aby uzyskać więcej informacji, zobacz [jak: uruchamiać częściowo zaufany kod w piaskownicy](how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="7a2de-137">For more information, see [How to: Run Partially Trusted Code in a Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="7a2de-138">Określanie bezpiecznego lub uzasadnionego zestawu uprawnień dla częściowo zaufanego kodu</span><span class="sxs-lookup"><span data-stu-id="7a2de-138">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="7a2de-139">Hosty często muszą określić uprawnienia, które są odpowiednie dla hostowanego kodu w trybie piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="7a2de-139">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="7a2de-140">Przed przystąpieniem do .NET Framework 4 zasady urzędów certyfikacji udostępniają <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="7a2de-140">Before the .NET Framework 4, CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7a2de-141">Jako zamiennik, .NET Framework 4 udostępnia <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> metodę, która zwraca bezpieczny, standardowy zestaw uprawnień dla dostarczonych dowodów.</span><span class="sxs-lookup"><span data-stu-id="7a2de-141">As a replacement, .NET Framework 4 provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="7a2de-142">Scenariusze spoza piaskownicy: przeciążenia dla obciążeń zestawu</span><span class="sxs-lookup"><span data-stu-id="7a2de-142">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="7a2de-143">Przyczyną użycia przeciążenia ładowania zestawu może być użycie parametrów, które nie są dostępne w inny sposób, zamiast w piaskownicy zestawu.</span><span class="sxs-lookup"><span data-stu-id="7a2de-143">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="7a2de-144">Począwszy od .NET Framework 4, przeciążenia ładowania zestawów, które nie wymagają <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> obiektu jako parametru, na przykład, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType> Włącz ten scenariusz.</span><span class="sxs-lookup"><span data-stu-id="7a2de-144">Starting with the .NET Framework 4, assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="7a2de-145">Jeśli chcesz piaskownicy zestawu, użyj <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> przeciążenia.</span><span class="sxs-lookup"><span data-stu-id="7a2de-145">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="7a2de-146">Zgodność: korzystanie z opcji starszej wersji zasad CAS</span><span class="sxs-lookup"><span data-stu-id="7a2de-146">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="7a2de-147">[ \<NetFx40_LegacySecurityPolicy> Element Configuration](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) pozwala określić, że proces lub biblioteka korzysta ze starszych zasad CAS.</span><span class="sxs-lookup"><span data-stu-id="7a2de-147">The [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="7a2de-148">Po włączeniu tego elementu przeciążenia zasad i dowodów będą działały tak, jak w poprzednich wersjach platformy.</span><span class="sxs-lookup"><span data-stu-id="7a2de-148">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="7a2de-149">Zachowanie zasad CAS jest określone w wersji środowiska uruchomieniowego, więc modyfikowanie zasad CAS dla jednej wersji środowiska uruchomieniowego nie ma wpływu na zasady CAS innej wersji.</span><span class="sxs-lookup"><span data-stu-id="7a2de-149">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7a2de-150">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7a2de-150">See also</span></span>

- [<span data-ttu-id="7a2de-151">Instrukcje: uruchamianie częściowo zaufanego kodu w piaskownicy</span><span class="sxs-lookup"><span data-stu-id="7a2de-151">How to: Run Partially Trusted Code in a Sandbox</span></span>](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="7a2de-152">Wytyczne dotyczące bezpiecznego programowania</span><span class="sxs-lookup"><span data-stu-id="7a2de-152">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
