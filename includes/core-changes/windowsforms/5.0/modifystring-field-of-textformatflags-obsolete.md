---
ms.openlocfilehash: 56127309c5f5993ffc2e2faedd1f481e8131e094
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400638"
---
### <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="03b68-101">TextFormatFlags. ModifyString jest przestarzała</span><span class="sxs-lookup"><span data-stu-id="03b68-101">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="03b68-102"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>Pole jest przestarzałe, jako ostrzeżenie i może zostać usunięte w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="03b68-102">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="03b68-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="03b68-103">Change description</span></span>

<span data-ttu-id="03b68-104">W poprzednich wersjach programu .NET <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> pole wyliczenia nie jest oznaczone jako przestarzałe.</span><span class="sxs-lookup"><span data-stu-id="03b68-104">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="03b68-105">W programie .NET 5,0 i jego nowszych wersjach jest oznaczona jako ostrzeżenie jako zaprzestarzała.</span><span class="sxs-lookup"><span data-stu-id="03b68-105">In .NET 5.0 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="03b68-106">To pole może zostać usunięte w przyszłej wersji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="03b68-106">This field may be removed in a future .NET version.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="03b68-107">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="03b68-107">Reason for change</span></span>

<span data-ttu-id="03b68-108">Przekazywanie ciągu do <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> przy użyciu <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> polecenia modyfikuje ciąg w niektórych sytuacjach.</span><span class="sxs-lookup"><span data-stu-id="03b68-108">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="03b68-109">To zachowanie przerywa niezmienności obietnicę i może prowadzić do krytycznego uszkodzenia stanu środowiska uruchomieniowego platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="03b68-109">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="03b68-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="03b68-110">Version introduced</span></span>

<span data-ttu-id="03b68-111">.NET 5,0 RC1</span><span class="sxs-lookup"><span data-stu-id="03b68-111">.NET 5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="03b68-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="03b68-112">Recommended action</span></span>

<span data-ttu-id="03b68-113">Aktualizowanie dowolnego kodu, który jest zależny od <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="03b68-113">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="03b68-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="03b68-114">Category</span></span>

<span data-ttu-id="03b68-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03b68-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="03b68-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="03b68-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

-->
