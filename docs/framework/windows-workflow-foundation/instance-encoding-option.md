---
title: Opcja kodowania wystąpienia
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 416394eb346a7c82385da32a89bd54179b255cd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279899"
---
# <a name="instance-encoding-option"></a><span data-ttu-id="82ebe-102">Opcja kodowania wystąpienia</span><span class="sxs-lookup"><span data-stu-id="82ebe-102">Instance Encoding Option</span></span>

<span data-ttu-id="82ebe-103">Właściwość **opcji kodowania wystąpienia** przepływu pracy SQL umożliwia określenie, czy dostawca trwałości SQL powinien kompresować informacje o stanie wystąpienia przepływu pracy przy użyciu algorytmu GZip przed zapisaniem informacji w bazie danych trwałości.</span><span class="sxs-lookup"><span data-stu-id="82ebe-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="82ebe-104">Dozwolone wartości tej właściwości to: GZip i none.</span><span class="sxs-lookup"><span data-stu-id="82ebe-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="82ebe-105">Wartość domyślna to Brak.</span><span class="sxs-lookup"><span data-stu-id="82ebe-105">The default value is None.</span></span> <span data-ttu-id="82ebe-106">Na poniższej liście opisano te opcje.</span><span class="sxs-lookup"><span data-stu-id="82ebe-106">The following list describes these options.</span></span>  
  
1. <span data-ttu-id="82ebe-107">**Gzip**.</span><span class="sxs-lookup"><span data-stu-id="82ebe-107">**GZip**.</span></span> <span data-ttu-id="82ebe-108">Dostawca trwałości koduje informacje o stanie przy użyciu algorytmu GZip przed utrwaleniem informacji o stanie w bazie danych trwałości.</span><span class="sxs-lookup"><span data-stu-id="82ebe-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2. <span data-ttu-id="82ebe-109">**Brak**.</span><span class="sxs-lookup"><span data-stu-id="82ebe-109">**None**.</span></span> <span data-ttu-id="82ebe-110">Dostawca trwałości nie koduje informacji o stanie przed zapisaniem informacji w bazie danych trwałości.</span><span class="sxs-lookup"><span data-stu-id="82ebe-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="82ebe-111">Kodowanie informacji o stanie wystąpienia przepływu pracy przy użyciu strumienia GZip zmniejsza zużycie pamięci w bazie danych SQL, a także zmniejsza zużycie sieci, jeśli baza danych znajduje się na innym komputerze w sieci z komputera, na którym jest uruchomiony Host usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="82ebe-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="82ebe-112">Ogólną wskazówką jest ustawienie dla właściwości **opcji kodowanie wystąpienia** wartości **Brak** , jeśli stan wystąpienia przepływu pracy jest niewielki.</span><span class="sxs-lookup"><span data-stu-id="82ebe-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
