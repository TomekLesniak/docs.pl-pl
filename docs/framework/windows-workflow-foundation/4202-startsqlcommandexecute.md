---
title: 4202 — StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: d3f27c6ed28efe9d099dcedfc676b839ae9b1dee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275843"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="08302-102">4202 — StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="08302-102">4202 - StartSqlCommandExecute</span></span>

## <a name="properties"></a><span data-ttu-id="08302-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="08302-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08302-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="08302-104">ID</span></span>|<span data-ttu-id="08302-105">4202</span><span class="sxs-lookup"><span data-stu-id="08302-105">4202</span></span>|  
|<span data-ttu-id="08302-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="08302-106">Keywords</span></span>|<span data-ttu-id="08302-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="08302-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="08302-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="08302-108">Level</span></span>|<span data-ttu-id="08302-109">Pełny</span><span class="sxs-lookup"><span data-stu-id="08302-109">Verbose</span></span>|  
|<span data-ttu-id="08302-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="08302-110">Channel</span></span>|<span data-ttu-id="08302-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="08302-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="08302-112">Opis</span><span class="sxs-lookup"><span data-stu-id="08302-112">Description</span></span>  

 <span data-ttu-id="08302-113">Wskazuje, że wykonywane jest polecenie SQL.</span><span class="sxs-lookup"><span data-stu-id="08302-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="08302-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="08302-114">Message</span></span>  

 <span data-ttu-id="08302-115">Uruchamianie wykonywania polecenia SQL: %1</span><span class="sxs-lookup"><span data-stu-id="08302-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="08302-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="08302-116">Details</span></span>  
  
|<span data-ttu-id="08302-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="08302-117">Data Item Name</span></span>|<span data-ttu-id="08302-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="08302-118">Data Item Type</span></span>|<span data-ttu-id="08302-119">Opis</span><span class="sxs-lookup"><span data-stu-id="08302-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="08302-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="08302-120">SqlCommand</span></span>|<span data-ttu-id="08302-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="08302-121">xs:string</span></span>|<span data-ttu-id="08302-122">Polecenie SQL, które zostało wykonane.</span><span class="sxs-lookup"><span data-stu-id="08302-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="08302-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="08302-123">AppDomain</span></span>|<span data-ttu-id="08302-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="08302-124">xs:string</span></span>|<span data-ttu-id="08302-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="08302-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
