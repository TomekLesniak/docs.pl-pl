---
ms.openlocfilehash: abcab63b5a90a70cc9dfabb031e94ce379e5471b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720207"
---
### <a name="parameter-names-changed-in-reference-assemblies"></a><span data-ttu-id="9e7f3-101">Nazwy parametrów zostały zmienione w zestawach odwołań</span><span class="sxs-lookup"><span data-stu-id="9e7f3-101">Parameter names changed in reference assemblies</span></span>

<span data-ttu-id="9e7f3-102">Niektóre nazwy parametrów zestawu odwołania zostały zmienione w celu dopasowania do nazw parametrów w zestawach implementacji.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-102">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9e7f3-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="9e7f3-103">Change description</span></span>

<span data-ttu-id="9e7f3-104">W poprzednich wersjach programu .NET niektóre nazwy parametrów [zestawu odwołania](../../../../docs/standard/assembly/reference-assemblies.md) są inne niż odpowiadające im parametry w zestawie implementacji.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-104">In previous .NET versions, some [reference assembly](../../../../docs/standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="9e7f3-105">Może to spowodować problemy podczas korzystania z nazwanych argumentów i odbicie.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-105">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="9e7f3-106">W programie .NET 5,0 te niezgodne nazwy parametrów zostały zaktualizowane w zestawach referencyjnych, aby dokładnie dopasować odpowiednie nazwy parametrów w zestawach implementacji.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-106">In .NET 5.0, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="9e7f3-107">W poniższej tabeli przedstawiono interfejsy API i nazwy parametrów, które uległy zmianie.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-107">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="9e7f3-108">interfejs API</span><span class="sxs-lookup"><span data-stu-id="9e7f3-108">API</span></span> | <span data-ttu-id="9e7f3-109">Stara nazwa parametru</span><span class="sxs-lookup"><span data-stu-id="9e7f3-109">Old parameter name</span></span> | <span data-ttu-id="9e7f3-110">Nazwa nowego parametru</span><span class="sxs-lookup"><span data-stu-id="9e7f3-110">New parameter name</span></span> |
| - | - | - |
| <xref:System.CodeDom.Compiler.CodeGenerator.GenerateStatements(System.CodeDom.CodeStatementCollection)?displayProperty=nameWithType> | `stms` | `stmts` |
| <xref:System.Drawing.Icon.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | `si` |
| <xref:System.Drawing.Image.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | `si` |
| <xref:System.Net.IPAddress.Parse(System.ReadOnlySpan{System.Char})?displayProperty=nameWithType> | `ipString` | `ipSpan` |
| <xref:System.Net.IPAddress.TryParse(System.ReadOnlySpan{System.Char},System.Net.IPAddress@)?displayProperty=nameWithType> | `ipString` | `ipSpan` |
| <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=nameWithType> | `buffer` | `array` |
| <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=nameWithType> | `buffer` | `array` |
| <xref:System.Net.NetworkCredential.GetCredential(System.String,System.Int32,System.String)?displayProperty=nameWithType> | `authType` | `authenticationType` |
| <xref:System.ComponentModel.ParenthesizePropertyNameAttribute.Equals(System.Object)?displayProperty=nameWithType> | `o` | `obj` |
| <xref:System.ComponentModel.RefreshPropertiesAttribute.Equals(System.Object)?displayProperty=nameWithType> | `value` | `obj` |
| <xref:System.Diagnostics.StackFrame.%23ctor(System.Boolean)> | `fNeedFileInfo` | `needFileInfo` |
| <xref:System.Diagnostics.StackFrame.%23ctor(System.Int32,System.Boolean)> | `fNeedFileInfo` | `needFileInfo` |
| <xref:System.StringNormalizationExtensions.IsNormalized(System.String,System.Text.NormalizationForm)?displayProperty=nameWithType> | `value` | `strInput` |
| <xref:System.StringNormalizationExtensions.IsNormalized(System.String)?displayProperty=nameWithType> | `value` | `strInput` |
| <xref:System.StringNormalizationExtensions.Normalize(System.String,System.Text.NormalizationForm)?displayProperty=nameWithType> | `value` | `strInput` |
| <xref:System.StringNormalizationExtensions.Normalize(System.String)?displayProperty=nameWithType> | `value` | `strInput` |

#### <a name="reason-for-change"></a><span data-ttu-id="9e7f3-111">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="9e7f3-111">Reason for change</span></span>

<span data-ttu-id="9e7f3-112">Nazwy parametrów zostały zmienione pod kątem spójności i w celu uniknięcia błędów przy użyciu nazwanych argumentów i odbicia.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-112">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9e7f3-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9e7f3-113">Version introduced</span></span>

<span data-ttu-id="9e7f3-114">5.0</span><span class="sxs-lookup"><span data-stu-id="9e7f3-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9e7f3-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="9e7f3-115">Recommended action</span></span>

<span data-ttu-id="9e7f3-116">Jeśli wystąpi błąd kompilatora z powodu zmiany nazwy parametru, należy odpowiednio zaktualizować nazwę parametru.</span><span class="sxs-lookup"><span data-stu-id="9e7f3-116">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

#### <a name="category"></a><span data-ttu-id="9e7f3-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="9e7f3-117">Category</span></span>

<span data-ttu-id="9e7f3-118">Podstawowe biblioteki platformy .NET</span><span class="sxs-lookup"><span data-stu-id="9e7f3-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9e7f3-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9e7f3-119">Affected APIs</span></span>

- <xref:System.CodeDom.Compiler.CodeGenerator.GenerateStatements(System.CodeDom.CodeStatementCollection)?displayProperty=fullName>
- <xref:System.ComponentModel.ParenthesizePropertyNameAttribute.Equals(System.Object)?displayProperty=fullName>
- <xref:System.ComponentModel.RefreshPropertiesAttribute.Equals(System.Object)?displayProperty=fullName>
- <xref:System.Diagnostics.StackFrame.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackFrame.%23ctor(System.Int32,System.Boolean)>
- <xref:System.Drawing.Icon.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=fullName>
- <xref:System.Drawing.Image.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=fullName>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.Net.IPAddress.Parse(System.ReadOnlySpan{System.Char})?displayProperty=fullName>
- <xref:System.Net.IPAddress.TryParse(System.ReadOnlySpan{System.Char},System.Net.IPAddress@)?displayProperty=fullName>
- <xref:System.Net.NetworkCredential.GetCredential(System.String,System.Int32,System.String)?displayProperty=fullName>
- <xref:System.StringNormalizationExtensions.IsNormalized(System.String,System.Text.NormalizationForm)?displayProperty=fullName>
- <xref:System.StringNormalizationExtensions.IsNormalized(System.String)?displayProperty=fullName>
- <xref:System.StringNormalizationExtensions.Normalize(System.String,System.Text.NormalizationForm)?displayProperty=fullName>
- <xref:System.StringNormalizationExtensions.Normalize(System.String)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.CodeDom.Compiler.CodeGenerator.GenerateStatements(System.CodeDom.CodeStatementCollection)`
- `M:System.Diagnostics.StackFrame.#ctor(System.Boolean)`
- `M:System.Diagnostics.StackFrame.#ctor(System.Int32,System.Boolean)`
- `M:System.Net.NetworkCredential.GetCredential(System.String,System.Int32,System.String)`
- `M:System.Net.IPAddress.Parse(System.ReadOnlySpan{System.Char})`
- `M:System.Net.IPAddress.TryParse(System.ReadOnlySpan{System.Char},System.Net.IPAddress@)`
- `M:System.StringNormalizationExtensions.IsNormalized(System.String,System.Text.NormalizationForm)`
- `M:System.StringNormalizationExtensions.IsNormalized(System.String)`
- `M:System.StringNormalizationExtensions.Normalize(System.String,System.Text.NormalizationForm)`
- `M:System.StringNormalizationExtensions.Normalize(System.String)`
- `M:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.ComponentModel.ParenthesizePropertyNameAttribute.Equals(System.Object)`
- `M:System.ComponentModel.RefreshPropertiesAttribute.Equals(System.Object)`
- `M:System.Drawing.Icon.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Drawing.Image.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`

-->
