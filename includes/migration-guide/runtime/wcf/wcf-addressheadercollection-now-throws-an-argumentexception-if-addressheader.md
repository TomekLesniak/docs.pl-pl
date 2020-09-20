---
ms.openlocfilehash: e8b98e465228afd07432e737bb16aefb1b979973
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770854"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="516b3-101">Funkcja WCF AddressHeaderCollection teraz generuje ArgumentException, jeśli element addressHeader ma wartość null</span><span class="sxs-lookup"><span data-stu-id="516b3-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="516b3-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="516b3-102">Details</span></span>

<span data-ttu-id="516b3-103">Rozpoczynając od .NET Framework 4.7.1, <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> Konstruktor zgłasza, <xref:System.ArgumentException> Jeśli jeden z elementów jest `null` .</span><span class="sxs-lookup"><span data-stu-id="516b3-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is `null`.</span></span> <span data-ttu-id="516b3-104">W .NET Framework 4,7 i wcześniejszych wersjach nie jest zgłaszany żaden wyjątek.</span><span class="sxs-lookup"><span data-stu-id="516b3-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="516b3-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="516b3-105">Suggestion</span></span>

<span data-ttu-id="516b3-106">Jeśli wystąpią problemy ze zgodnością z tą zmianą w .NET Framework 4.7.1 lub nowszej wersji, możesz zrezygnować z niej, dodając następujący wiersz do `<runtime>` sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="516b3-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true" />
  </runtime>
</configuration>

| Name    | Value   |
|:--------|:--------|
| Scope   | Minor   |
| Version | 4.7.1   |
| Type    | Runtime |

#### Affected APIs

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
