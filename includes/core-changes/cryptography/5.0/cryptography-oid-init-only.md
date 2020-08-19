---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558010"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="13184-101">System. Security. Cryptography. OID jest funkcjonalnie init-Only</span><span class="sxs-lookup"><span data-stu-id="13184-101">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="13184-102"><xref:System.Security.Cryptography.Oid?displayProperty=fullName>Klasa, która jest używana do reprezentowania wartości identyfikatora obiektu ASN. 1 oraz ich "przyjaznych" nazw, była poprzednio w pełni modyfikowalna.</span><span class="sxs-lookup"><span data-stu-id="13184-102">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="13184-103">Ten zmienność był często zaszukiwany lub nieoczekiwany.</span><span class="sxs-lookup"><span data-stu-id="13184-103">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="13184-104">Metody ustawiające właściwości teraz generują <xref:System.PlatformNotSupportedException> podczas próby zmiany wartości po jej przypisaniu.</span><span class="sxs-lookup"><span data-stu-id="13184-104">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

#### <a name="change-description"></a><span data-ttu-id="13184-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="13184-105">Change description</span></span>

<span data-ttu-id="13184-106">W poprzednich wersjach metody ustawiające właściwości on <xref:System.Security.Cryptography.Oid> mogą służyć do zmiany wartości <xref:System.Security.Cryptography.Oid.FriendlyName> <xref:System.Security.Cryptography.Oid.Value> właściwości i.</span><span class="sxs-lookup"><span data-stu-id="13184-106">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="13184-107">W programie .NET 5,0 i nowszych wersjach metody ustawiające właściwości mogą być używane tylko w celu zainicjowania wartości.</span><span class="sxs-lookup"><span data-stu-id="13184-107">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="13184-108">Gdy właściwość ma wartość, albo z konstruktora lub poprzedniego wywołania metody ustawiającej właściwość, Metoda ustawiająca Właściwość zawsze zgłasza <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="13184-108">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="13184-109">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="13184-109">Reason for change</span></span>

<span data-ttu-id="13184-110">Ta zmiana umożliwia ponowne użycie <xref:System.Security.Cryptography.Oid> obiektów jako część wartości zwracanych w publicznych interfejsach API w celu zmniejszenia profilów alokacji obiektów.</span><span class="sxs-lookup"><span data-stu-id="13184-110">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="13184-111">Pozwala to uniknąć konieczności tworzenia tymczasowych kopii "obronnych", gdy <xref:System.Security.Cryptography.Oid> wartości są używane jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="13184-111">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="13184-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="13184-112">Version introduced</span></span>

<span data-ttu-id="13184-113">5,0 wersja zapoznawcza 8</span><span class="sxs-lookup"><span data-stu-id="13184-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="13184-114">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="13184-114">Recommended action</span></span>

<span data-ttu-id="13184-115">Unikaj używania metod <xref:System.Security.Cryptography.Oid> ustawiających właściwości innych niż w przypadku inicjowania obiektu.</span><span class="sxs-lookup"><span data-stu-id="13184-115">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="13184-116">Aby reprezentować nową wartość, Użyj nowego wystąpienia zamiast zmieniać wartość istniejącego obiektu.</span><span class="sxs-lookup"><span data-stu-id="13184-116">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

#### <a name="category"></a><span data-ttu-id="13184-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="13184-117">Category</span></span>

<span data-ttu-id="13184-118">Kryptografia</span><span class="sxs-lookup"><span data-stu-id="13184-118">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="13184-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="13184-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
