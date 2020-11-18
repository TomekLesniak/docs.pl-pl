---
title: 'Instrukcje: Przywracanie stref czasowych z zasobu osadzonego'
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], deserializing
- time zones [.NET], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: a1302f595a0907103bae2695e703e5af6da660a7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817669"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="92483-102">Instrukcje: Przywracanie stref czasowych z zasobu osadzonego</span><span class="sxs-lookup"><span data-stu-id="92483-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="92483-103">W tym temacie opisano sposób przywracania stref czasowych, które zostały zapisane w pliku zasobów.</span><span class="sxs-lookup"><span data-stu-id="92483-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="92483-104">Aby uzyskać informacje i instrukcje dotyczące zapisywania stref czasowych, zobacz [How to: Save Time Zones to a Embedded Resource](save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="92483-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="92483-105">Aby deserializować obiekt TimeZoneInfo z osadzonego zasobu</span><span class="sxs-lookup"><span data-stu-id="92483-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="92483-106">Jeśli strefa czasowa do pobrania nie jest niestandardową strefą czasową, spróbuj ją utworzyć przy użyciu <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="92483-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="92483-107">Utworzenie wystąpienia <xref:System.Resources.ResourceManager> obiektu przez przekazanie w pełni kwalifikowanej nazwy osadzonego pliku zasobów i odwołania do zestawu zawierającego plik zasobów.</span><span class="sxs-lookup"><span data-stu-id="92483-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="92483-108">Jeśli nie można określić w pełni kwalifikowanej nazwy osadzonego pliku zasobów, użyj [Ildasm.exe (Il dezasembler)](../../framework/tools/ildasm-exe-il-disassembler.md) , aby sprawdzić manifest zestawu.</span><span class="sxs-lookup"><span data-stu-id="92483-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="92483-109">`.mresource`Wpis identyfikuje zasób.</span><span class="sxs-lookup"><span data-stu-id="92483-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="92483-110">W tym przykładzie w pełni kwalifikowana nazwa zasobu to `SerializeTimeZoneData.SerializedTimeZones` .</span><span class="sxs-lookup"><span data-stu-id="92483-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="92483-111">Jeśli plik zasobów jest osadzony w tym samym zestawie, który zawiera kod tworzenia wystąpienia strefy czasowej, można pobrać odwołanie do niego, wywołując `static` `Shared` metodę (w Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> .</span><span class="sxs-lookup"><span data-stu-id="92483-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="92483-112">Jeśli wywołanie <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metody nie powiedzie się lub jeśli zostanie utworzona niestandardowa strefa czasowa, Pobierz ciąg zawierający serializowaną strefę czasową, wywołując <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="92483-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="92483-113">Deserializacja danych strefy czasowej przez wywołanie <xref:System.TimeZoneInfo.FromSerializedString%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="92483-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="92483-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="92483-114">Example</span></span>

<span data-ttu-id="92483-115">Poniższy przykład deserializacji <xref:System.TimeZoneInfo> obiekt przechowywany w osadzonym pliku zasobów XML programu .NET.</span><span class="sxs-lookup"><span data-stu-id="92483-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="92483-116">Ten kod ilustruje obsługę wyjątków, aby upewnić się, że <xref:System.TimeZoneInfo> istnieje obiekt wymagany przez aplikację.</span><span class="sxs-lookup"><span data-stu-id="92483-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="92483-117">Najpierw próbuje utworzyć wystąpienie <xref:System.TimeZoneInfo> obiektu, pobierając go z rejestru przy użyciu <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="92483-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="92483-118">Jeśli nie można utworzyć wystąpienia strefy czasowej, kod pobiera go z osadzonego pliku zasobów.</span><span class="sxs-lookup"><span data-stu-id="92483-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="92483-119">Ponieważ dane dla niestandardowych stref czasowych (strefy czasowe tworzone przy użyciu <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metody) nie są przechowywane w rejestrze, kod nie wywołuje w <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> celu utworzenia wystąpienia strefy czasowej dla Palmer, Antarktyda.</span><span class="sxs-lookup"><span data-stu-id="92483-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="92483-120">Zamiast tego natychmiast szuka osadzony plik zasobów, aby pobrać ciąg, który zawiera dane strefy czasowej przed wywołaniem <xref:System.TimeZoneInfo.FromSerializedString%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="92483-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="92483-121">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="92483-121">Compiling the code</span></span>

<span data-ttu-id="92483-122">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="92483-122">This example requires:</span></span>

- <span data-ttu-id="92483-123">To odwołanie do System.Windows.Forms.dll i System.Core.dll zostać dodane do projektu.</span><span class="sxs-lookup"><span data-stu-id="92483-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="92483-124">Że importowane są następujące przestrzenie nazw:</span><span class="sxs-lookup"><span data-stu-id="92483-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="92483-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="92483-125">See also</span></span>

- [<span data-ttu-id="92483-126">Daty, godziny i strefy czasowe</span><span class="sxs-lookup"><span data-stu-id="92483-126">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="92483-127">Strefy czasowe — omówienie</span><span class="sxs-lookup"><span data-stu-id="92483-127">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="92483-128">Instrukcje: Zapisywanie stref czasowych w zasobie osadzonym</span><span class="sxs-lookup"><span data-stu-id="92483-128">How to: Save time zones to an embedded resource</span></span>](save-time-zones-to-an-embedded-resource.md)
