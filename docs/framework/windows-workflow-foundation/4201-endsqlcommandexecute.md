---
title: 4201 — EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 0d6326889077e36ad49aa6267ae7285849c6818d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275869"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="bfc2a-102">4201 — EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="bfc2a-102">4201 - EndSqlCommandExecute</span></span>

## <a name="properties"></a><span data-ttu-id="bfc2a-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="bfc2a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bfc2a-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="bfc2a-104">ID</span></span>|<span data-ttu-id="bfc2a-105">4201</span><span class="sxs-lookup"><span data-stu-id="bfc2a-105">4201</span></span>|  
|<span data-ttu-id="bfc2a-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="bfc2a-106">Keywords</span></span>|<span data-ttu-id="bfc2a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="bfc2a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="bfc2a-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="bfc2a-108">Level</span></span>|<span data-ttu-id="bfc2a-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="bfc2a-109">Verbose</span></span>|  
|<span data-ttu-id="bfc2a-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="bfc2a-110">Channel</span></span>|<span data-ttu-id="bfc2a-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="bfc2a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bfc2a-112">Opis</span><span class="sxs-lookup"><span data-stu-id="bfc2a-112">Description</span></span>  

 <span data-ttu-id="bfc2a-113">Wskazuje, że polecenie SQL zakończyło wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="bfc2a-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bfc2a-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="bfc2a-114">Message</span></span>  

 <span data-ttu-id="bfc2a-115">Zakończenie wykonywania polecenia SQL: %1</span><span class="sxs-lookup"><span data-stu-id="bfc2a-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="bfc2a-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="bfc2a-116">Details</span></span>  
  
|<span data-ttu-id="bfc2a-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="bfc2a-117">Data Item Name</span></span>|<span data-ttu-id="bfc2a-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="bfc2a-118">Data Item Type</span></span>|<span data-ttu-id="bfc2a-119">Opis</span><span class="sxs-lookup"><span data-stu-id="bfc2a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bfc2a-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="bfc2a-120">SqlCommand</span></span>|<span data-ttu-id="bfc2a-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="bfc2a-121">xs:string</span></span>|<span data-ttu-id="bfc2a-122">Polecenie SQL, które zostało wykonane.</span><span class="sxs-lookup"><span data-stu-id="bfc2a-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="bfc2a-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="bfc2a-123">AppDomain</span></span>|<span data-ttu-id="bfc2a-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="bfc2a-124">xs:string</span></span>|<span data-ttu-id="bfc2a-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bfc2a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
