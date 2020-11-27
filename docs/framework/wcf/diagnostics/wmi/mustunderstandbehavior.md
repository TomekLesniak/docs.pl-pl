---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 9cac7192d5c34de55fe0bd6a4921a41387e985f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250440"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="e6980-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="e6980-102">MustUnderstandBehavior</span></span>

<span data-ttu-id="e6980-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="e6980-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6980-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e6980-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e6980-105">Metody</span><span class="sxs-lookup"><span data-stu-id="e6980-105">Methods</span></span>  

 <span data-ttu-id="e6980-106">Klasa MustUnderstandBehavior nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="e6980-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e6980-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e6980-107">Properties</span></span>  

 <span data-ttu-id="e6980-108">Klasa MustUnderstandBehavior ma następującą właściwość:</span><span class="sxs-lookup"><span data-stu-id="e6980-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="e6980-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="e6980-109">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="e6980-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="e6980-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="e6980-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="e6980-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e6980-112">Gdy `true` wszystkie nagłówki protokołu SOAP z `MustUnderstand` atrybutem, który nie jest obsługiwany, powodują zgłoszenie wyjątku.</span><span class="sxs-lookup"><span data-stu-id="e6980-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6980-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e6980-113">Requirements</span></span>  
  
|<span data-ttu-id="e6980-114">PLIK</span><span class="sxs-lookup"><span data-stu-id="e6980-114">MOF</span></span>|<span data-ttu-id="e6980-115">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="e6980-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e6980-116">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="e6980-116">Namespace</span></span>|<span data-ttu-id="e6980-117">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e6980-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6980-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e6980-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
