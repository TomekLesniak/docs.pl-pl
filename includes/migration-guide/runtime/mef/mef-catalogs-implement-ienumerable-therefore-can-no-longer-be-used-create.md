---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496397"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="11c8e-101">Wykazy MEF implementują interfejs IEnumerable i w związku z tym nie mogą być już używane do tworzenia serializatora</span><span class="sxs-lookup"><span data-stu-id="11c8e-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="11c8e-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="11c8e-102">Details</span></span>

<span data-ttu-id="11c8e-103">Począwszy od .NET Framework 4,5, wykazy MEF implementują interfejs IEnumerable i w związku z tym nie można już używać do tworzenia serializatora ( <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> obiektu).</span><span class="sxs-lookup"><span data-stu-id="11c8e-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="11c8e-104">Próba serializowania katalogu MEF powoduje zgłoszenie wyjątku.</span><span class="sxs-lookup"><span data-stu-id="11c8e-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="11c8e-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="11c8e-105">Suggestion</span></span>

<span data-ttu-id="11c8e-106">Nie można już używać MEF do tworzenia serializatora</span><span class="sxs-lookup"><span data-stu-id="11c8e-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="11c8e-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="11c8e-107">Name</span></span>    | <span data-ttu-id="11c8e-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="11c8e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="11c8e-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="11c8e-109">Scope</span></span>   |<span data-ttu-id="11c8e-110">Duży</span><span class="sxs-lookup"><span data-stu-id="11c8e-110">Major</span></span>|
|<span data-ttu-id="11c8e-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="11c8e-111">Version</span></span>|<span data-ttu-id="11c8e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="11c8e-112">4.5</span></span>|
|<span data-ttu-id="11c8e-113">Typ</span><span class="sxs-lookup"><span data-stu-id="11c8e-113">Type</span></span>|<span data-ttu-id="11c8e-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="11c8e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="11c8e-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="11c8e-115">Affected APIs</span></span>

<span data-ttu-id="11c8e-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="11c8e-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
