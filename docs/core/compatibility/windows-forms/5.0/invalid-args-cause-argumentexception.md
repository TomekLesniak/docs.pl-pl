---
title: 'Zmiana istotna: metody WinForms teraz generują ArgumentException'
description: Dowiedz się więcej o istotnej zmianie w programie .NET 5,0, gdzie metody sWindows Forms teraz generują ArgumentException dla nieprawidłowych argumentów.
ms.date: 07/18/2020
ms.openlocfilehash: 46fe3f3b1208a5cd676e1b7546507bed36a850f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761716"
---
# <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="fd8de-103">Metody WinForms teraz generują ArgumentException</span><span class="sxs-lookup"><span data-stu-id="fd8de-103">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="fd8de-104">Niektóre metody Windows Forms teraz generują <xref:System.ArgumentException> dla nieprawidłowych argumentów, w których wcześniej nie zostały.</span><span class="sxs-lookup"><span data-stu-id="fd8de-104">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="fd8de-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="fd8de-105">Change description</span></span>

<span data-ttu-id="fd8de-106">Wcześniej przekazywanie argumentów nieoczekiwanego lub nieprawidłowego typu do określonych metod Windows Forms spowoduje nieokreślony stan.</span><span class="sxs-lookup"><span data-stu-id="fd8de-106">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="fd8de-107">Począwszy od platformy .NET 5,0, metody te generują teraz, <xref:System.ArgumentException> gdy przekazane nieprawidłowe argumenty.</span><span class="sxs-lookup"><span data-stu-id="fd8de-107">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="fd8de-108">Zgłaszanie jest <xref:System.ArgumentException> zgodne z zachowaniem środowiska uruchomieniowego .NET.</span><span class="sxs-lookup"><span data-stu-id="fd8de-108">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="fd8de-109">Usprawnia to również środowisko debugowania, przez co jasno komunikuje się, który argument jest nieprawidłowy.</span><span class="sxs-lookup"><span data-stu-id="fd8de-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="fd8de-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="fd8de-110">Version introduced</span></span>

<span data-ttu-id="fd8de-111">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="fd8de-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="fd8de-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="fd8de-112">Recommended action</span></span>

- <span data-ttu-id="fd8de-113">Zaktualizuj kod, aby zapobiec przekazywaniu nieprawidłowych argumentów.</span><span class="sxs-lookup"><span data-stu-id="fd8de-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="fd8de-114">W razie potrzeby dojście do <xref:System.ArgumentException> wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="fd8de-114">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="fd8de-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="fd8de-115">Affected APIs</span></span>

<span data-ttu-id="fd8de-116">Poniższa tabela zawiera listę odpowiednich metod i parametrów:</span><span class="sxs-lookup"><span data-stu-id="fd8de-116">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="fd8de-117">Metoda</span><span class="sxs-lookup"><span data-stu-id="fd8de-117">Method</span></span> | <span data-ttu-id="fd8de-118">Nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="fd8de-118">Parameter name</span></span> | <span data-ttu-id="fd8de-119">Warunek</span><span class="sxs-lookup"><span data-stu-id="fd8de-119">Condition</span></span> | <span data-ttu-id="fd8de-120">Dodana wersja</span><span class="sxs-lookup"><span data-stu-id="fd8de-120">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="fd8de-121">Argument nie jest typu <xref:System.Windows.Forms.TabPage> .</span><span class="sxs-lookup"><span data-stu-id="fd8de-121">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="fd8de-122">Wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="fd8de-122">Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="fd8de-123">Argument to `null` , <xref:System.String.Empty?displayProperty=nameWithType> lub biały znak.</span><span class="sxs-lookup"><span data-stu-id="fd8de-123">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="fd8de-124">Wersja zapoznawcza 5</span><span class="sxs-lookup"><span data-stu-id="fd8de-124">Preview 5</span></span> |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | <span data-ttu-id="fd8de-125">Nie można pobrać elementu `InputLanguage` dla określonej kultury.</span><span class="sxs-lookup"><span data-stu-id="fd8de-125">Unable to retrieve an `InputLanguage` for the specified culture.</span></span> | <span data-ttu-id="fd8de-126">Wersja zapoznawcza 7</span><span class="sxs-lookup"><span data-stu-id="fd8de-126">Preview 7</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

### Category

Windows Forms

-->
