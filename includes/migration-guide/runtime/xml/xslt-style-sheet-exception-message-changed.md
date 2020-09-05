---
ms.openlocfilehash: d33d75b4c2d9bc18844f66f1fcca1e2efc6f1eee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496427"
---
### <a name="xslt-style-sheet-exception-message-changed"></a><span data-ttu-id="bbaae-101">Zmieniono komunikat o wyjątku arkusza stylów XSLT</span><span class="sxs-lookup"><span data-stu-id="bbaae-101">XSLT style sheet exception message changed</span></span>

#### <a name="details"></a><span data-ttu-id="bbaae-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="bbaae-102">Details</span></span>

<span data-ttu-id="bbaae-103">W .NET Framework 4,5 tekst komunikatu o błędzie, gdy plik XSLT jest zbyt złożony, to &quot; arkusz stylów jest zbyt złożony. &quot; W poprzednich wersjach komunikat o błędzie był &quot; błędem kompilacji XSLT. &quot; Kod aplikacji, który zależy od tekstu komunikatu o błędzie, przestanie działać.</span><span class="sxs-lookup"><span data-stu-id="bbaae-103">In the .NET Framework 4.5, the text of the error message when an XSLT file is too complex is &quot;The style sheet is too complex.&quot; In previous versions, the error message was &quot;XSLT compile error.&quot; Application code that depends on the text of the error message will no longer work.</span></span> <span data-ttu-id="bbaae-104">Jednak typy wyjątków pozostają takie same, więc zmiana ta nie powinna mieć rzeczywistego wpływu.</span><span class="sxs-lookup"><span data-stu-id="bbaae-104">However, the exception types remain the same, so this change should have no real impact.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bbaae-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="bbaae-105">Suggestion</span></span>

<span data-ttu-id="bbaae-106">Zaktualizuj dowolny kod aplikacji w zależności od komunikatu o wyjątku z tego warunku błędu, aby oczekiwać nowej wiadomości lub (nawet lepiej) zaktualizować kod, tak aby był zależny tylko od typu wyjątku ( <xref:System.Xml.Xsl.XsltException?displayProperty=fullName> ), który nie został zmieniony.</span><span class="sxs-lookup"><span data-stu-id="bbaae-106">Update any app code depending on the exception message from this error condition to expect the new message, or (even better) update the code to depend only on the exception type (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), which has not changed.</span></span>

| <span data-ttu-id="bbaae-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="bbaae-107">Name</span></span>    | <span data-ttu-id="bbaae-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="bbaae-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bbaae-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="bbaae-109">Scope</span></span>   |<span data-ttu-id="bbaae-110">Edge</span><span class="sxs-lookup"><span data-stu-id="bbaae-110">Edge</span></span>|
|<span data-ttu-id="bbaae-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="bbaae-111">Version</span></span>|<span data-ttu-id="bbaae-112">4.5</span><span class="sxs-lookup"><span data-stu-id="bbaae-112">4.5</span></span>|
|<span data-ttu-id="bbaae-113">Typ</span><span class="sxs-lookup"><span data-stu-id="bbaae-113">Type</span></span>|<span data-ttu-id="bbaae-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="bbaae-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="bbaae-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="bbaae-115">Affected APIs</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.String)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`

-->
