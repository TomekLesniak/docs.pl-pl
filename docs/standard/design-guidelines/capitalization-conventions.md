---
title: Konwencje dotyczące wielkości liter
description: Stosowanie Konwencji kapitalizacji dla identyfikatorów, słów złożonych i typowych warunków. Dowiedz się, jak działa czułość wielkości liter w programie .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8df136fb57ad61ddfd87f4dec1f6490c63c3d977
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821531"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="ec824-104">Konwencje dotyczące wielkości liter</span><span class="sxs-lookup"><span data-stu-id="ec824-104">Capitalization Conventions</span></span>
<span data-ttu-id="ec824-105">Wytyczne w tym rozdziale określają prostą metodę używania przypadku, która jest stosowana spójnie, dzięki czemu identyfikatory typów, elementów członkowskich i parametrów łatwo odczytać.</span><span class="sxs-lookup"><span data-stu-id="ec824-105">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="ec824-106">Reguły dotyczące wersalików dla identyfikatorów</span><span class="sxs-lookup"><span data-stu-id="ec824-106">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="ec824-107">Aby rozróżnić słowa w identyfikatorze, należy zrobić wielką literę każdego wyrazu w identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="ec824-107">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="ec824-108">Nie należy używać podkreśleń do rozróżniania wyrazów lub dla tego znaczenia, gdziekolwiek w identyfikatorach.</span><span class="sxs-lookup"><span data-stu-id="ec824-108">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="ec824-109">Istnieją dwa odpowiednie sposoby na wielkie litery, w zależności od użycia identyfikatora:</span><span class="sxs-lookup"><span data-stu-id="ec824-109">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="ec824-110">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="ec824-110">PascalCasing</span></span>

- <span data-ttu-id="ec824-111">camelCasing</span><span class="sxs-lookup"><span data-stu-id="ec824-111">camelCasing</span></span>

 <span data-ttu-id="ec824-112">Konwencja PascalCasing używana dla wszystkich identyfikatorów z wyjątkiem nazw parametrów, wielką literą w pierwszym znaku każdego wyrazu (w tym akronimów przez dwie litery), jak pokazano w następujących przykładach:</span><span class="sxs-lookup"><span data-stu-id="ec824-112">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="ec824-113">Szczególny przypadek jest tworzony w przypadku dwuliterowych akronimów, w których obie litery są pisane wielkimi literami, jak pokazano w poniższym identyfikatorze:</span><span class="sxs-lookup"><span data-stu-id="ec824-113">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="ec824-114">Konwencja camelCasing używana tylko w przypadku nazw parametrów, wielką literą pierwszego znaku każdego wyrazu, z wyjątkiem pierwszego wyrazu, jak pokazano w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="ec824-114">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="ec824-115">Jak widać również przykład, dwuliterowe akronimy, które rozpoczynają notacji CamelCase identyfikator, są zarówno małymi literami.</span><span class="sxs-lookup"><span data-stu-id="ec824-115">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="ec824-116">✔️ używać PascalCasing dla wszystkich publicznych elementów członkowskich, typów i nazw, składających się z wielu wyrazów.</span><span class="sxs-lookup"><span data-stu-id="ec824-116">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="ec824-117">✔️ używać camelCasing do nazw parametrów.</span><span class="sxs-lookup"><span data-stu-id="ec824-117">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="ec824-118">W poniższej tabeli opisano reguły dotyczące wielkich liter dla różnych typów identyfikatorów.</span><span class="sxs-lookup"><span data-stu-id="ec824-118">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="ec824-119">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="ec824-119">Identifier</span></span>|<span data-ttu-id="ec824-120">Wielkość liter</span><span class="sxs-lookup"><span data-stu-id="ec824-120">Casing</span></span>|<span data-ttu-id="ec824-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="ec824-121">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="ec824-122">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="ec824-122">Namespace</span></span>|<span data-ttu-id="ec824-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-123">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="ec824-124">Typ</span><span class="sxs-lookup"><span data-stu-id="ec824-124">Type</span></span>|<span data-ttu-id="ec824-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-125">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="ec824-126">Interfejs</span><span class="sxs-lookup"><span data-stu-id="ec824-126">Interface</span></span>|<span data-ttu-id="ec824-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-127">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="ec824-128">Metoda</span><span class="sxs-lookup"><span data-stu-id="ec824-128">Method</span></span>|<span data-ttu-id="ec824-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-129">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="ec824-130">Właściwość</span><span class="sxs-lookup"><span data-stu-id="ec824-130">Property</span></span>|<span data-ttu-id="ec824-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-131">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="ec824-132">Zdarzenie</span><span class="sxs-lookup"><span data-stu-id="ec824-132">Event</span></span>|<span data-ttu-id="ec824-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-133">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="ec824-134">Pole</span><span class="sxs-lookup"><span data-stu-id="ec824-134">Field</span></span>|<span data-ttu-id="ec824-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-135">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="ec824-136">Wartość wyliczenia</span><span class="sxs-lookup"><span data-stu-id="ec824-136">Enum value</span></span>|<span data-ttu-id="ec824-137">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-137">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="ec824-138">Parametr</span><span class="sxs-lookup"><span data-stu-id="ec824-138">Parameter</span></span>|<span data-ttu-id="ec824-139">Camel</span><span class="sxs-lookup"><span data-stu-id="ec824-139">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="ec824-140">Wielkie litery słów i typowe terminy</span><span class="sxs-lookup"><span data-stu-id="ec824-140">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="ec824-141">Większość postanowień złożonych jest traktowanych jako pojedyncze słowa do celów wielkich liter.</span><span class="sxs-lookup"><span data-stu-id="ec824-141">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="ec824-142">❌ NIE używaj wielkich liter w każdym słowie, tak jak w przypadku wyrazów złożonych.</span><span class="sxs-lookup"><span data-stu-id="ec824-142">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="ec824-143">Są to wyrazy złożone zapisywane jako pojedyncze słowo, takie jak punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="ec824-143">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="ec824-144">Aby zapoznać się z wytycznymi dotyczącymi wielkości liter, Traktuj zamknięty wyraz złożony jako pojedynczy wyraz.</span><span class="sxs-lookup"><span data-stu-id="ec824-144">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="ec824-145">Użyj bieżącego słownika, aby określić, czy złożone słowo jest zapisywana w zamkniętym formularzu.</span><span class="sxs-lookup"><span data-stu-id="ec824-145">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="ec824-146">Pascal</span><span class="sxs-lookup"><span data-stu-id="ec824-146">Pascal</span></span>|<span data-ttu-id="ec824-147">Camel</span><span class="sxs-lookup"><span data-stu-id="ec824-147">Camel</span></span>|<span data-ttu-id="ec824-148">Not</span><span class="sxs-lookup"><span data-stu-id="ec824-148">Not</span></span>|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a><span data-ttu-id="ec824-149">Rozróżnianie wielkości liter</span><span class="sxs-lookup"><span data-stu-id="ec824-149">Case Sensitivity</span></span>
 <span data-ttu-id="ec824-150">Języki, które mogą być uruchamiane w środowisku CLR, nie są wymagane do obsługi rozróżniania wielkości liter, chociaż niektóre z nich wykonują.</span><span class="sxs-lookup"><span data-stu-id="ec824-150">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="ec824-151">Nawet jeśli język obsługuje tę funkcję, inne języki, które mogą uzyskać dostęp do platformy, nie.</span><span class="sxs-lookup"><span data-stu-id="ec824-151">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="ec824-152">Wszystkie interfejsy API, które są dostępne z zewnątrz, w związku z tym nie mogą polegać na przypadku odróżnienia dwóch nazw w tym samym kontekście.</span><span class="sxs-lookup"><span data-stu-id="ec824-152">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="ec824-153">❌ NIE należy zakładać, że wszystkie języki programowania uwzględniają wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="ec824-153">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="ec824-154">Nie są.</span><span class="sxs-lookup"><span data-stu-id="ec824-154">They are not.</span></span> <span data-ttu-id="ec824-155">Nazwy nie mogą różnić się w zależności od wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="ec824-155">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="ec824-156">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="ec824-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ec824-157">*Ponownie Wydrukowano przez uprawnienie Pearson Education, Inc. z [wytycznych dotyczących projektowania platformy: konwencje, idiomy i wzorce dla bibliotek .NET do wielokrotnego użytku, 2. wydanie](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) przez Krzysztof Cwalina i Brad Abrams, opublikowane 22, 2008 przez Addison-Wesley Professional w ramach serii Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="ec824-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ec824-158">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ec824-158">See also</span></span>

- [<span data-ttu-id="ec824-159">Wskazówki dotyczące projektowania struktury</span><span class="sxs-lookup"><span data-stu-id="ec824-159">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="ec824-160">Wskazówki dotyczące nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="ec824-160">Naming Guidelines</span></span>](naming-guidelines.md)
