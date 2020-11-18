---
title: Zabezpieczanie danych o stanie
description: Zadeklaruj dane stanu jako zmienne prywatne lub wewnętrzne, aby ograniczyć dostęp do niego. Dostęp do tych danych można nadal uzyskać poprzez odbicie, serializację i debugowanie.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: 849ed993befaceda1b04becbb7fb2530c5c62a77
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824164"
---
# <a name="securing-state-data"></a><span data-ttu-id="849fb-104">Zabezpieczanie danych o stanie</span><span class="sxs-lookup"><span data-stu-id="849fb-104">Securing State Data</span></span>

<span data-ttu-id="849fb-105">Aplikacje, które obsługują dane poufne lub podejmują jakiekolwiek decyzje dotyczące zabezpieczeń, muszą zachować te dane w ramach własnych kontroli i nie mogą być bezpośrednio dostępne w innym potencjalnie złośliwym kodzie.</span><span class="sxs-lookup"><span data-stu-id="849fb-105">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="849fb-106">Najlepszym sposobem ochrony danych w pamięci jest zadeklarowanie danych jako prywatnych lub wewnętrznych (z zakresem ograniczonym do tego samego zestawu).</span><span class="sxs-lookup"><span data-stu-id="849fb-106">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="849fb-107">Jednak nawet te dane podlegają dostępowi, należy pamiętać o:</span><span class="sxs-lookup"><span data-stu-id="849fb-107">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="849fb-108">Korzystanie z mechanizmów odbicia, wysoce zaufany kod, który może odwoływać się do obiektu, może pobierać i ustawiać prywatnych członków.</span><span class="sxs-lookup"><span data-stu-id="849fb-108">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="849fb-109">Przy użyciu serializacji wysoce zaufany kod może efektywnie uzyskać i ustawić prywatne składowe, jeśli ma dostęp do odpowiednich danych w serializowanej formie obiektu.</span><span class="sxs-lookup"><span data-stu-id="849fb-109">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="849fb-110">W obszarze Debugowanie można odczytać te dane.</span><span class="sxs-lookup"><span data-stu-id="849fb-110">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="849fb-111">Upewnij się, że żadna z własnych metod lub właściwości nie ujawnia tych wartości przypadkowo.</span><span class="sxs-lookup"><span data-stu-id="849fb-111">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="849fb-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="849fb-112">See also</span></span>

- [<span data-ttu-id="849fb-113">Wytyczne dotyczące bezpiecznego programowania</span><span class="sxs-lookup"><span data-stu-id="849fb-113">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="849fb-114">Zabezpieczenia ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="849fb-114">ASP.NET Core Security</span></span>](/aspnet/core/security/)
