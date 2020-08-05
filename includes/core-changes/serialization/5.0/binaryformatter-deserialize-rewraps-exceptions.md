---
ms.openlocfilehash: 4aef35502fc93cbf0399e3c8d0932338829d6c07
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517359"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="390a2-101">BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException</span><span class="sxs-lookup"><span data-stu-id="390a2-101">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="390a2-102"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>Metoda teraz ponownie pakuje niektóre obiekty wyjątków wewnątrz a <xref:System.Runtime.Serialization.SerializationException> przed propagacją wyjątku z powrotem do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="390a2-102">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

#### <a name="change-description"></a><span data-ttu-id="390a2-103">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="390a2-103">Change description</span></span>

<span data-ttu-id="390a2-104">Wcześniej <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> Metoda umożliwiała niektóre dowolne wyjątki, takie jak <xref:System.ArgumentNullException> , aby propagować stos do jego obiektów wywołujących.</span><span class="sxs-lookup"><span data-stu-id="390a2-104">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="390a2-105">W programie .NET 5,0 i nowszych <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> Metoda bardziej agresywnie przechwytuje wyjątki, które występują z powodu nieprawidłowych operacji deserializacji i zawija je w <xref:System.Runtime.Serialization.SerializationException> .</span><span class="sxs-lookup"><span data-stu-id="390a2-105">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="390a2-106">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="390a2-106">Version introduced</span></span>

<span data-ttu-id="390a2-107">5,0 wersja zapoznawcza 1</span><span class="sxs-lookup"><span data-stu-id="390a2-107">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="390a2-108">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="390a2-108">Recommended action</span></span>

<span data-ttu-id="390a2-109">W większości przypadków nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="390a2-109">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="390a2-110">Jeśli jednak lokacja wywołania zależy od zgłoszonego wyjątku, można Odpakuj wyjątek z elementu zewnętrznego <xref:System.Runtime.Serialization.SerializationException> , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="390a2-110">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx)
{
    if (serEx.InnerException is MyException myEx)
    {
        // Handle 'myEx' here in case it was wrapped in SerializationException.
    }
    else
    {
        throw;
    }
}
```

#### <a name="category"></a><span data-ttu-id="390a2-111">Kategoria</span><span class="sxs-lookup"><span data-stu-id="390a2-111">Category</span></span>

<span data-ttu-id="390a2-112">Serializacja</span><span class="sxs-lookup"><span data-stu-id="390a2-112">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="390a2-113">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="390a2-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->
