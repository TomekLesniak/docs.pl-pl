---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496875"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a><span data-ttu-id="417e6-101">BinaryFormatter może nie można znaleźć typu z kontekstu LoadFrom</span><span class="sxs-lookup"><span data-stu-id="417e6-101">BinaryFormatter can fail to find type from LoadFrom context</span></span>

#### <a name="details"></a><span data-ttu-id="417e6-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="417e6-102">Details</span></span>

<span data-ttu-id="417e6-103">W przypadku .NET Framework 4,5 wiele <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> zmian może spowodować różnice w deserializacji podczas korzystania z programu w <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> celu deserializacji typów, które zostały załadowane w kontekście LoadFrom.</span><span class="sxs-lookup"><span data-stu-id="417e6-103">As of .NET Framework 4.5, a number of <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> changes may cause differences in deserialization when using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> to deserialize types that had been loaded in the LoadFrom context.</span></span> <span data-ttu-id="417e6-104">Te zmiany są spowodowane nowymi sposobami, <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> teraz ładuje typ, który powoduje inne zachowanie podczas <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> próby deserializacji do tego typu w późniejszym czasie.</span><span class="sxs-lookup"><span data-stu-id="417e6-104">These changes are due to the new ways <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> now loads a type which causes different behavior when a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> attempts to deserialize to that type later on.</span></span> <span data-ttu-id="417e6-105">Domyślny spinacz serializacji nie przeszukuje automatycznie kontekstu LoadFrom, chociaż może pracował w pewnych okolicznościach w oparciu o stare zachowanie elementu XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="417e6-105">The default serialization binder does not automatically search the LoadFrom context, although it may have worked in some circumstances based on the old behavior of XmlSerializer.</span></span> <span data-ttu-id="417e6-106">Ze względu na zmiany, gdy typ jest ładowany z zestawu załadowanego w innym kontekście, <xref:System.IO.FileNotFoundException?displayProperty=fullName> może zostać zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="417e6-106">Due to the changes, when a type is being loaded from an assembly loaded in a different context, a <xref:System.IO.FileNotFoundException?displayProperty=fullName> may be thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="417e6-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="417e6-107">Suggestion</span></span>

<span data-ttu-id="417e6-108">Jeśli ten wyjątek jest widoczny, <code>Binder</code> Właściwość <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> można ustawić na niestandardowy spinacz, który będzie znajdować poprawny typ.</span><span class="sxs-lookup"><span data-stu-id="417e6-108">If this exception is seen, the <code>Binder</code> property of the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> can be set to a custom binder that will find the correct type.</span></span><pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre><span data-ttu-id="417e6-109">A następnie niestandardowy spinacz:</span><span class="sxs-lookup"><span data-stu-id="417e6-109">And then the custom binder:</span></span><pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="417e6-110">Nazwa</span><span class="sxs-lookup"><span data-stu-id="417e6-110">Name</span></span>    | <span data-ttu-id="417e6-111">Wartość</span><span class="sxs-lookup"><span data-stu-id="417e6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="417e6-112">Zakres</span><span class="sxs-lookup"><span data-stu-id="417e6-112">Scope</span></span>   |<span data-ttu-id="417e6-113">Edge</span><span class="sxs-lookup"><span data-stu-id="417e6-113">Edge</span></span>|
|<span data-ttu-id="417e6-114">Wersja</span><span class="sxs-lookup"><span data-stu-id="417e6-114">Version</span></span>|<span data-ttu-id="417e6-115">4.5</span><span class="sxs-lookup"><span data-stu-id="417e6-115">4.5</span></span>|
|<span data-ttu-id="417e6-116">Typ</span><span class="sxs-lookup"><span data-stu-id="417e6-116">Type</span></span>|<span data-ttu-id="417e6-117">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="417e6-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="417e6-118">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="417e6-118">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
