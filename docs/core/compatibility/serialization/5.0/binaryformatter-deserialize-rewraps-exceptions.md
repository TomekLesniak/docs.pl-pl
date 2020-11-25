---
title: 'Nieprzerwana zmiana: BinaryFormatter. deserializacji odpakuje niektóre wyjątki'
description: Dowiedz się więcej na temat istotnej zmiany w programie .NET 5,0, gdzie BinaryFormatter. defragmentuje odpakuje niektóre obiekty wyjątków wewnątrz SerializationException.
ms.date: 08/18/2020
ms.openlocfilehash: 90dc4cce6785fdb38644cca2a2e9aff65eb7a313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761432"
---
# <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="9a743-103">BinaryFormatter. defragmentuje odpakuje niektóre wyjątki w SerializationException</span><span class="sxs-lookup"><span data-stu-id="9a743-103">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="9a743-104"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>Metoda teraz ponownie pakuje niektóre obiekty wyjątków wewnątrz a <xref:System.Runtime.Serialization.SerializationException> przed propagacją wyjątku z powrotem do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="9a743-104">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

## <a name="change-description"></a><span data-ttu-id="9a743-105">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="9a743-105">Change description</span></span>

<span data-ttu-id="9a743-106">Wcześniej <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> Metoda umożliwiała niektóre dowolne wyjątki, takie jak <xref:System.ArgumentNullException> , aby propagować stos do jego obiektów wywołujących.</span><span class="sxs-lookup"><span data-stu-id="9a743-106">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="9a743-107">W programie .NET 5,0 i nowszych <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> Metoda bardziej agresywnie przechwytuje wyjątki, które występują z powodu nieprawidłowych operacji deserializacji i zawija je w <xref:System.Runtime.Serialization.SerializationException> .</span><span class="sxs-lookup"><span data-stu-id="9a743-107">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="9a743-108">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="9a743-108">Version introduced</span></span>

<span data-ttu-id="9a743-109">5,0</span><span class="sxs-lookup"><span data-stu-id="9a743-109">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="9a743-110">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="9a743-110">Recommended action</span></span>

<span data-ttu-id="9a743-111">W większości przypadków nie trzeba podejmować żadnych działań.</span><span class="sxs-lookup"><span data-stu-id="9a743-111">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="9a743-112">Jeśli jednak lokacja wywołania zależy od zgłoszonego wyjątku, można Odpakuj wyjątek z elementu zewnętrznego <xref:System.Runtime.Serialization.SerializationException> , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9a743-112">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

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
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

## <a name="affected-apis"></a><span data-ttu-id="9a743-113">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="9a743-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

### Category

Serialization

-->
