---
ms.openlocfilehash: 6ffd4147a99a59d0a2e50d3f88279608e286aed1
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679952"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a><span data-ttu-id="6230e-101">CryptoStream. Dispose przekształca końcowy blok tylko podczas pisania</span><span class="sxs-lookup"><span data-stu-id="6230e-101">CryptoStream.Dispose transforms final block only when writing</span></span>

<span data-ttu-id="6230e-102"><xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType>Metoda, która jest używana do kończenia `CryptoStream` operacji, nie próbuje przekształcić końcowego bloku podczas odczytu.</span><span class="sxs-lookup"><span data-stu-id="6230e-102">The <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> method, which is used to finish `CryptoStream` operations, no longer attempts to transform the final block when reading.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6230e-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="6230e-103">Change description</span></span>

<span data-ttu-id="6230e-104">W poprzednich wersjach platformy .NET, jeśli użytkownik wykonał niekompletny odczyt podczas korzystania <xref:System.Security.Cryptography.CryptoStream> z <xref:System.Security.Cryptography.CryptoStreamMode.Read> trybu, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> Metoda może zgłosić wyjątek (na przykład w przypadku użycia algorytmu AES z uzupełnieniem).</span><span class="sxs-lookup"><span data-stu-id="6230e-104">In previous .NET versions, if a user performed an incomplete read when using <xref:System.Security.Cryptography.CryptoStream> in <xref:System.Security.Cryptography.CryptoStreamMode.Read> mode, the <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> method could throw an exception (for example, when using AES with padding).</span></span> <span data-ttu-id="6230e-105">Wyjątek został zgłoszony, ponieważ ostatni podjęto próbę przekształcenia końcowego bloku, ale dane były niekompletne.</span><span class="sxs-lookup"><span data-stu-id="6230e-105">The exception was thrown because the final block was attempted to be transformed but the data was incomplete.</span></span>

<span data-ttu-id="6230e-106">W programie .NET Core 3,0 i jego nowszych wersjach program <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> nie próbuje przekształcić końcowego bloku podczas odczytywania, co pozwala na niekompletne odczyty.</span><span class="sxs-lookup"><span data-stu-id="6230e-106">In .NET Core 3.0 and later versions, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> no longer tries to transform the final block when reading, which allows for incomplete reads.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6230e-107">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="6230e-107">Reason for change</span></span>

<span data-ttu-id="6230e-108">Ta zmiana włącza niekompletne odczyty ze strumienia kryptograficznego po anulowaniu operacji sieciowej, bez konieczności przechwytywania wyjątku.</span><span class="sxs-lookup"><span data-stu-id="6230e-108">This change enables incomplete reads from the crypto stream when a network operation is canceled, without the need to catch an exception.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6230e-109">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="6230e-109">Version introduced</span></span>

<span data-ttu-id="6230e-110">3,0</span><span class="sxs-lookup"><span data-stu-id="6230e-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6230e-111">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="6230e-111">Recommended action</span></span>

<span data-ttu-id="6230e-112">Ta zmiana nie powinna mieć wpływ na większość aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6230e-112">Most apps should not be affected by this change.</span></span>

<span data-ttu-id="6230e-113">Jeśli aplikacja wcześniej przechwyciła wyjątek w przypadku niekompletnego odczytu, można usunąć ten `catch` blok.</span><span class="sxs-lookup"><span data-stu-id="6230e-113">If your application previously caught an exception in case of an incomplete read, you can delete that `catch` block.</span></span>
<span data-ttu-id="6230e-114">Jeśli Twoja aplikacja użyła przekształcenia końcowego w scenariusze tworzenia skrótów, może być konieczne upewnienie się, że cały strumień jest odczytywany przed jego usunięciem.</span><span class="sxs-lookup"><span data-stu-id="6230e-114">If your app used transforming of the final block in hashing scenarios, you might need to ensure that the entire stream is read before it's disposed.</span></span>

#### <a name="category"></a><span data-ttu-id="6230e-115">Kategoria</span><span class="sxs-lookup"><span data-stu-id="6230e-115">Category</span></span>

<span data-ttu-id="6230e-116">Kryptografia</span><span class="sxs-lookup"><span data-stu-id="6230e-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6230e-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="6230e-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
