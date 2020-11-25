---
title: 'Nieprzerwana zmiana: MulticastOption. Group nie akceptuje wartości null.'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, gdzie MulticastOption. Group nie akceptuje już wartości null.
ms.date: 08/18/2020
ms.openlocfilehash: 164ac8c2c8dd14f9e0758017e54eeb377f88a7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761439"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a><span data-ttu-id="55e9d-103">MulticastOption. Group nie akceptuje wartości null</span><span class="sxs-lookup"><span data-stu-id="55e9d-103">MulticastOption.Group doesn't accept a null value</span></span>

<span data-ttu-id="55e9d-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> nie akceptuje już wartości `null` .</span><span class="sxs-lookup"><span data-stu-id="55e9d-104"><xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> no longer accepts a value of `null`.</span></span> <span data-ttu-id="55e9d-105">Jeśli właściwość zostanie ustawiona na `null` , <xref:System.ArgumentNullException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="55e9d-105">If you set the property to `null`, an <xref:System.ArgumentNullException> is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="55e9d-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="55e9d-106">Version introduced</span></span>

<span data-ttu-id="55e9d-107">5,0</span><span class="sxs-lookup"><span data-stu-id="55e9d-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="55e9d-108">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="55e9d-108">Change description</span></span>

<span data-ttu-id="55e9d-109">We wcześniejszych wersjach programu .NET można ustawić <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> Właściwość na `null` .</span><span class="sxs-lookup"><span data-stu-id="55e9d-109">In previous versions of .NET, you can set the <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> property to `null`.</span></span> <span data-ttu-id="55e9d-110">Jeśli <xref:System.Net.Sockets.MulticastOption> przeszedł później do <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> , środowisko uruchomieniowe wygeneruje <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="55e9d-110">If the <xref:System.Net.Sockets.MulticastOption> is later passed to <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, the runtime throws a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="55e9d-111">W programie .NET 5,0 i nowszych <xref:System.ArgumentNullException> jest zgłaszany, jeśli właściwość zostanie ustawiona na `null` .</span><span class="sxs-lookup"><span data-stu-id="55e9d-111">In .NET 5.0 and later, an <xref:System.ArgumentNullException> is thrown if you set the property to `null`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="55e9d-112">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="55e9d-112">Reason for change</span></span>

<span data-ttu-id="55e9d-113">Aby zachować zgodność ze wskazówkami dotyczącymi projektowania struktury, właściwość została zaktualizowana w celu wygenerowania <xref:System.ArgumentNullException> wartości `null` .</span><span class="sxs-lookup"><span data-stu-id="55e9d-113">To be consistent with the Framework Design Guidelines, the property has been updated to throw an <xref:System.ArgumentNullException> if the value is `null`.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="55e9d-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="55e9d-114">Recommended action</span></span>

<span data-ttu-id="55e9d-115">Upewnij się, że nie ustawiono <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> opcji `null` .</span><span class="sxs-lookup"><span data-stu-id="55e9d-115">Make sure that you don't set <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> to `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="55e9d-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="55e9d-116">Affected APIs</span></span>

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
