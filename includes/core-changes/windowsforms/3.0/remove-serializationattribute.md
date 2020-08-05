---
ms.openlocfilehash: 4fb1ffed97a5b7f906bed13a69f1e71563d11dae
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556216"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a><span data-ttu-id="9ca6b-101">SerializableAttribute usunięte z niektórych typów Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ca6b-101">SerializableAttribute removed from some Windows Forms types</span></span>

<span data-ttu-id="9ca6b-102">Program <xref:System.SerializableAttribute> został usunięty z niektórych klas Windows Forms, które nie mają znanych scenariuszy serializacji binarnej.</span><span class="sxs-lookup"><span data-stu-id="9ca6b-102">The <xref:System.SerializableAttribute> has been removed from some Windows Forms classes that have no known binary serialization scenarios.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9ca6b-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="9ca6b-103">Change description</span></span>

<span data-ttu-id="9ca6b-104">Następujące typy są dekoracyjne <xref:System.SerializableAttribute> w .NET Framework, ale atrybut został usunięty z platformy .NET Core:</span><span class="sxs-lookup"><span data-stu-id="9ca6b-104">The following types are decorated with the <xref:System.SerializableAttribute> in .NET Framework, but the attribute has been removed in .NET Core:</span></span>

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

<span data-ttu-id="9ca6b-105">W przeszłości ten mechanizm serializacji miał poważne problemy związane z konserwacją i bezpieczeństwem.</span><span class="sxs-lookup"><span data-stu-id="9ca6b-105">Historically, this serialization mechanism has had serious maintenance and security concerns.</span></span> <span data-ttu-id="9ca6b-106">Utrzymywanie `SerializableAttribute` na typach oznacza, że te typy muszą być testowane pod kątem zmian serializacji z wersji do wersji oraz ewentualnych zmian serializacji między platformami.</span><span class="sxs-lookup"><span data-stu-id="9ca6b-106">Maintaining `SerializableAttribute` on types means those types must be tested for version-to-version serialization changes and potentially framework-to-framework serialization changes.</span></span> <span data-ttu-id="9ca6b-107">Dzięki temu trudniej jest rozwijać te typy i mogą być kosztowne do utrzymania.</span><span class="sxs-lookup"><span data-stu-id="9ca6b-107">This makes it harder to evolve those types and can be costly to maintain.</span></span> <span data-ttu-id="9ca6b-108">Te typy nie mają znanych scenariuszy serializacji binarnej, co minimalizuje wpływ usuwania atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9ca6b-108">These types have no known binary serialization scenarios, which minimizes the impact of removing the attribute.</span></span>

<span data-ttu-id="9ca6b-109">Aby uzyskać więcej informacji, zobacz [Serializacja binarna](~/docs/standard/serialization/binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="9ca6b-109">For more information, see [Binary serialization](~/docs/standard/serialization/binary-serialization.md).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9ca6b-110">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9ca6b-110">Version introduced</span></span>

<span data-ttu-id="9ca6b-111">3.0</span><span class="sxs-lookup"><span data-stu-id="9ca6b-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9ca6b-112">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="9ca6b-112">Recommended action</span></span>

<span data-ttu-id="9ca6b-113">Zaktualizuj każdy kod, który może zależeć od tych typów jako możliwy do serializacji.</span><span class="sxs-lookup"><span data-stu-id="9ca6b-113">Update any code that may depend on these types being marked as serializable.</span></span>

#### <a name="category"></a><span data-ttu-id="9ca6b-114">Kategoria</span><span class="sxs-lookup"><span data-stu-id="9ca6b-114">Category</span></span>

<span data-ttu-id="9ca6b-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ca6b-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9ca6b-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9ca6b-116">Affected APIs</span></span>

- <span data-ttu-id="9ca6b-117">Brak</span><span class="sxs-lookup"><span data-stu-id="9ca6b-117">None</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
