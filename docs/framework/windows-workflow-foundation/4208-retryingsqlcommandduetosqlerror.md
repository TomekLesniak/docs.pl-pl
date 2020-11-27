---
title: 4208 — RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 088754cb15c2e55faa1d43a1da1c79ddcddd69f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280419"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="e3d73-102">4208 — RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="e3d73-102">4208 - RetryingSqlCommandDueToSqlError</span></span>

## <a name="properties"></a><span data-ttu-id="e3d73-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="e3d73-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3d73-104">ID (Identyfikator)</span><span class="sxs-lookup"><span data-stu-id="e3d73-104">ID</span></span>|<span data-ttu-id="e3d73-105">4208</span><span class="sxs-lookup"><span data-stu-id="e3d73-105">4208</span></span>|  
|<span data-ttu-id="e3d73-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="e3d73-106">Keywords</span></span>|<span data-ttu-id="e3d73-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="e3d73-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="e3d73-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="e3d73-108">Level</span></span>|<span data-ttu-id="e3d73-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="e3d73-109">Information</span></span>|  
|<span data-ttu-id="e3d73-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="e3d73-110">Channel</span></span>|<span data-ttu-id="e3d73-111">Microsoft-Windows-Application Server — aplikacje/debugowanie</span><span class="sxs-lookup"><span data-stu-id="e3d73-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e3d73-112">Opis</span><span class="sxs-lookup"><span data-stu-id="e3d73-112">Description</span></span>  

 <span data-ttu-id="e3d73-113">Wskazuje, że dostawca SQL próbuje wykonać polecenie SQL z powodu błędu SQL.</span><span class="sxs-lookup"><span data-stu-id="e3d73-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e3d73-114">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="e3d73-114">Message</span></span>  

 <span data-ttu-id="e3d73-115">Ponawianie próby wykonania polecenia SQL z powodu błędu SQL o numerze %1.</span><span class="sxs-lookup"><span data-stu-id="e3d73-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e3d73-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="e3d73-116">Details</span></span>  
  
|<span data-ttu-id="e3d73-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="e3d73-117">Data Item Name</span></span>|<span data-ttu-id="e3d73-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="e3d73-118">Data Item Type</span></span>|<span data-ttu-id="e3d73-119">Opis</span><span class="sxs-lookup"><span data-stu-id="e3d73-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e3d73-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="e3d73-120">ErrorNumber</span></span>|<span data-ttu-id="e3d73-121">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e3d73-121">xs:string</span></span>|<span data-ttu-id="e3d73-122">Numer błędu SQL.</span><span class="sxs-lookup"><span data-stu-id="e3d73-122">The SQL error number.</span></span>|  
|<span data-ttu-id="e3d73-123">Wywołując</span><span class="sxs-lookup"><span data-stu-id="e3d73-123">AppDomain</span></span>|<span data-ttu-id="e3d73-124">XS: ciąg</span><span class="sxs-lookup"><span data-stu-id="e3d73-124">xs:string</span></span>|<span data-ttu-id="e3d73-125">Ciąg zwracany przez element AppDomain. CurrentDomain —. FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e3d73-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
