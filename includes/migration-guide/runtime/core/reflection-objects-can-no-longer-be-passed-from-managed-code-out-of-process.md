---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497022"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="66bb6-101">Obiektów odbicia nie można już przekazywać z kodu zarządzanego do pozaprocesowych klientów DCOM.</span><span class="sxs-lookup"><span data-stu-id="66bb6-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="66bb6-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="66bb6-102">Details</span></span>

<span data-ttu-id="66bb6-103">Obiektów odbicia nie można już przekazywać z kodu zarządzanego do pozaprocesowych klientów DCOM.</span><span class="sxs-lookup"><span data-stu-id="66bb6-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="66bb6-104">Dotyczy to następujących typów:</span><span class="sxs-lookup"><span data-stu-id="66bb6-104">The following types are affected:</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <span data-ttu-id="66bb6-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (i jego typy pochodne, w tym <xref:System.Reflection.FieldInfo?displayProperty=fullName> , <xref:System.Reflection.MethodInfo?displayProperty=fullName> , <xref:System.Type?displayProperty=fullName> i <xref:System.Reflection.TypeInfo?displayProperty=fullName> )</span><span class="sxs-lookup"><span data-stu-id="66bb6-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

<span data-ttu-id="66bb6-106">Wywołania do <code>IMarshal</code> zwracanego obiektu <code>E_NOINTERFACE</code> .</span><span class="sxs-lookup"><span data-stu-id="66bb6-106">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="66bb6-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="66bb6-107">Suggestion</span></span>

<span data-ttu-id="66bb6-108">Aktualizuj kod kierujący do pracy z obiektami nieodbicia.</span><span class="sxs-lookup"><span data-stu-id="66bb6-108">Update marshaling code to work with non-reflection objects.</span></span>

| <span data-ttu-id="66bb6-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="66bb6-109">Name</span></span>    | <span data-ttu-id="66bb6-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="66bb6-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="66bb6-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="66bb6-111">Scope</span></span>   |<span data-ttu-id="66bb6-112">Mały</span><span class="sxs-lookup"><span data-stu-id="66bb6-112">Minor</span></span>|
|<span data-ttu-id="66bb6-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="66bb6-113">Version</span></span>|<span data-ttu-id="66bb6-114">4,6</span><span class="sxs-lookup"><span data-stu-id="66bb6-114">4.6</span></span>|
|<span data-ttu-id="66bb6-115">Typ</span><span class="sxs-lookup"><span data-stu-id="66bb6-115">Type</span></span>|<span data-ttu-id="66bb6-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="66bb6-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="66bb6-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="66bb6-117">Affected APIs</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
