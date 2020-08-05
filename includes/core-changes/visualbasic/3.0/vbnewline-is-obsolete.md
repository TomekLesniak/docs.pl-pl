---
ms.openlocfilehash: 072ed716910e2e1f1f98dbddc56d5bd097b75acc
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555916"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="31068-101">Microsoft. VisualBasic. Stałychs. vbNewLine jest przestarzała</span><span class="sxs-lookup"><span data-stu-id="31068-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="31068-102"><xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>Stała jest oznaczona jako [ \[ przestarzała \] ](xref:System.ObsoleteAttribute) począwszy od platformy .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="31068-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked as [\[Obsolete\]](xref:System.ObsoleteAttribute) starting with .NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="31068-103">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="31068-103">Version introduced</span></span>

<span data-ttu-id="31068-104">3.0</span><span class="sxs-lookup"><span data-stu-id="31068-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="31068-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="31068-105">Change description</span></span>

<span data-ttu-id="31068-106">Począwszy od platformy .NET Core 3,0, [przestarzały](xref:System.ObsoleteAttribute) atrybut został zastosowany do <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> stałej.</span><span class="sxs-lookup"><span data-stu-id="31068-106">Starting with .NET Core 3.0, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="31068-107">Użycie stałej powoduje wygenerowanie ostrzeżenia kompilatora.</span><span class="sxs-lookup"><span data-stu-id="31068-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="31068-108">W .NET Framework i poprzednich wersjach programu .NET Core nie została oznaczona jako przestarzała.</span><span class="sxs-lookup"><span data-stu-id="31068-108">In .NET Framework and previous releases of .NET Core, it was not marked as obsolete.</span></span>

<span data-ttu-id="31068-109">Ta zmiana została wprowadzona w celu obsługi Visual Basic jako języka dla tworzenia wielu platform.</span><span class="sxs-lookup"><span data-stu-id="31068-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="31068-110"><xref:Microsoft.VisualBasic.Constants.vbNewLine>Stała jest równoznaczna z `\r\n` sekwencją znaków nowego wiersza w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="31068-110">The <xref:Microsoft.VisualBasic.Constants.vbNewLine> constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="31068-111">W systemach opartych na systemie UNIX znak nowego wiersza to `\n` .</span><span class="sxs-lookup"><span data-stu-id="31068-111">On Unix-based systems, the newline character is `\n`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="31068-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="31068-112">Recommended action</span></span>

<span data-ttu-id="31068-113">Komunikat o [przestarzałym](xref:System.ObsoleteAttribute) atrybucie dla programu <xref:Microsoft.VisualBasic.Constants.vbNewLine> zawiera następujące zalecenia:</span><span class="sxs-lookup"><span data-stu-id="31068-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for <xref:Microsoft.VisualBasic.Constants.vbNewLine> includes the following recommendation:</span></span>

<span data-ttu-id="31068-114">W przypadku powrotu karetki i wysuwu wiersza Użyj <xref:Microsoft.VisualBasic.Constants.vbCrLf> .</span><span class="sxs-lookup"><span data-stu-id="31068-114">For a carriage return and line feed, use <xref:Microsoft.VisualBasic.Constants.vbCrLf>.</span></span> <span data-ttu-id="31068-115">W przypadku wiersza dla bieżącej platformy Użyj <xref:System.Environment.NewLine?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="31068-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="31068-116">Kategoria</span><span class="sxs-lookup"><span data-stu-id="31068-116">Category</span></span>

<span data-ttu-id="31068-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31068-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="31068-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="31068-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

#### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
