---
title: Znajdowanie oświadczeń w zestawie oświadczeń
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: c43a47b32a2a3c15d1a51b8b6931ebb021722a64
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268459"
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="c24c0-102">Znajdowanie oświadczeń w zestawie oświadczeń</span><span class="sxs-lookup"><span data-stu-id="c24c0-102">Finding Claims in a ClaimSet</span></span>

<span data-ttu-id="c24c0-103">Badanie zawartości a <xref:System.IdentityModel.Claims.ClaimSet> dla określonych typów oświadczeń jest typowym zadaniem podczas korzystania z autoryzacji opartej na oświadczeniach.</span><span class="sxs-lookup"><span data-stu-id="c24c0-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="c24c0-104">Aby poznać <xref:System.IdentityModel.Claims.ClaimSet> obecność określonych oświadczeń, należy użyć <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="c24c0-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="c24c0-105">Ta metoda zapewnia lepszą wydajność niż iteracja bezpośrednio w usłudze <xref:System.IdentityModel.Claims.ClaimSet> .</span><span class="sxs-lookup"><span data-stu-id="c24c0-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="c24c0-106">Poniższy przykład ilustruje to użycie.</span><span class="sxs-lookup"><span data-stu-id="c24c0-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="c24c0-107">Należy pamiętać, `claimType` że `claimRight` Parametry i mogą być `null` .</span><span class="sxs-lookup"><span data-stu-id="c24c0-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="c24c0-108">W takim przypadku parametry będą zgodne ze wszystkimi typami i prawami roszczeń.</span><span class="sxs-lookup"><span data-stu-id="c24c0-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c24c0-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="c24c0-109">Example</span></span>  

 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c24c0-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c24c0-110">See also</span></span>

- [<span data-ttu-id="c24c0-111">Zarządzanie oświadczeniami i autoryzacją za pomocą modelu tożsamości</span><span class="sxs-lookup"><span data-stu-id="c24c0-111">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
