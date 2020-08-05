---
ms.openlocfilehash: d69f619522c7abc3171f1c089e53cc2754899f93
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556224"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="8a890-101">Nieobsługiwany przełącznik zgodności UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="8a890-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="8a890-102">`Switch.System.Windows.Forms.UseLegacyImages`Przełącznik zgodności, który został wprowadzony w .NET Framework 4,8, nie jest obsługiwany w Windows Forms na platformie .NET Core lub .net 5,0 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="8a890-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8a890-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="8a890-103">Change description</span></span>

<span data-ttu-id="8a890-104">Począwszy od .NET Framework 4,8, przełącznik zgodności zapoznajł `Switch.System.Windows.Forms.UseLegacyImages` możliwe problemy z skalowaniem obrazu w scenariuszach ClickOnce w środowiskach o wysokiej rozdzielczości DPI.</span><span class="sxs-lookup"><span data-stu-id="8a890-104">Starting with .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="8a890-105">Gdy ustawiona `true` jest wartość, przełącznik umożliwia użytkownikowi przywrócenie starszego skalowania obrazu na wyświetlaczach o wysokiej rozdzielczości DPI, których Skala jest ustawiona na wartość większą niż 100%.</span><span class="sxs-lookup"><span data-stu-id="8a890-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="8a890-106">Aby uzyskać więcej informacji, zobacz [Informacje o wersji .NET Framework 4,8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) w witrynie GitHub.</span><span class="sxs-lookup"><span data-stu-id="8a890-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="8a890-107">W przypadku programów .NET Core i .NET 5,0 i nowszych `Switch.System.Windows.Forms.UseLegacyImages` przełącznik nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="8a890-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8a890-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="8a890-108">Version introduced</span></span>

<span data-ttu-id="8a890-109">3.0</span><span class="sxs-lookup"><span data-stu-id="8a890-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8a890-110">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="8a890-110">Recommended action</span></span>

<span data-ttu-id="8a890-111">Usuń przełącznik.</span><span class="sxs-lookup"><span data-stu-id="8a890-111">Remove the switch.</span></span> <span data-ttu-id="8a890-112">Przełącznik nie jest obsługiwany i żadna alternatywna funkcja nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="8a890-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="8a890-113">Kategoria</span><span class="sxs-lookup"><span data-stu-id="8a890-113">Category</span></span>

<span data-ttu-id="8a890-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8a890-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8a890-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="8a890-115">Affected APIs</span></span>

- <span data-ttu-id="8a890-116">Brak</span><span class="sxs-lookup"><span data-stu-id="8a890-116">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
