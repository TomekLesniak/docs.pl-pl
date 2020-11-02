---
title: 'Instrukcje: konwertowanie między strumieniami .NET Framework i środowisko wykonawcze systemu Windows (tylko system Windows)'
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
ms.openlocfilehash: 7833dd16cec8d6ef1cbdb51702ea72f50231c52d
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187960"
---
# <a name="how-to-convert-between-net-framework-and-windows-runtime-streams-windows-only"></a>Instrukcje: konwertowanie między strumieniami .NET Framework i środowisko wykonawcze systemu Windows (tylko system Windows)

.NET Framework for platformy UWP Apps to podzbiór pełnych .NET Framework. Ze względu na bezpieczeństwo i inne wymagania dotyczące aplikacji platformy UWP nie można używać pełnego zestawu .NET Framework interfejsów API do otwierania i odczytywania plików. Aby uzyskać więcej informacji, zobacz temat [Omówienie aplikacji .net for platformy UWP](/previous-versions/windows/apps/br230302(v=vs.140)). Jednak może być wymagane użycie interfejsów API programu .NET Framework w celu wykonywania innych operacji na strumieniach. Aby manipulować tymi strumieniami, można dokonać konwersji między typem strumienia .NET Framework, takim jak <xref:System.IO.MemoryStream> lub <xref:System.IO.FileStream> i strumieniem środowisko wykonawcze systemu Windows, takim jak <xref:Windows.Storage.Streams.IInputStream> , <xref:Windows.Storage.Streams.IOutputStream> lub <xref:Windows.Storage.Streams.IRandomAccessStream> .

<xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType>Klasa zawiera metody, które ułatwiają wykonywanie tych konwersji. Jednak podstawowe różnice między strumieniami .NET Framework i środowisko wykonawcze systemu Windows wpływają na wyniki korzystania z tych metod, zgodnie z opisem w poniższych sekcjach:

## <a name="convert-from-a-windows-runtime-to-a-net-framework-stream"></a>Konwertowanie środowisko wykonawcze systemu Windows na strumień .NET Framework
Aby przekonwertować strumień środowisko wykonawcze systemu Windows do strumienia .NET Framework, użyj jednej z następujących <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType> metod:

- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A?displayProperty=nameWithType> Konwertuje strumień dostępu swobodnego w środowisko wykonawcze systemu Windows na zarządzany strumień w programie .NET for platformy UWP Apps.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite%2A?displayProperty=nameWithType> Konwertuje strumień wyjściowy w środowisko wykonawcze systemu Windows na zarządzany strumień w programie .NET for platformy UWP Apps.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A?displayProperty=nameWithType> Konwertuje strumień wejściowy w środowisko wykonawcze systemu Windows na zarządzany strumień w programie .NET for platformy UWP Apps.

Środowisko wykonawcze systemu Windows oferuje typy strumieni obsługujące tylko odczyt, tylko do zapisu i odczytywanie i zapisywanie. Te funkcje są utrzymywane podczas konwertowania strumienia środowisko wykonawcze systemu Windows do strumienia .NET Framework. Co więcej, po przekonwertowaniu strumienia środowiska wykonawczego systemu Windows na strumień programu .NET Framework i z powrotem jest przywracane oryginalne wystąpienie strumienia środowiska wykonawczego systemu Windows.

Najlepszym rozwiązaniem jest użycie metody konwersji, która jest zgodna z możliwościami strumienia środowisko wykonawcze systemu Windows, które chcesz skonwertować. Jednak ponieważ <xref:Windows.Storage.Streams.IRandomAccessStream> jest możliwy do odczytu i zapisu (implementuje zarówno <xref:Windows.Storage.Streams.IOutputStream> i <xref:Windows.Storage.Streams.IInputStream> ), metody konwersji zachowują możliwości oryginalnego strumienia. Na przykład użycie <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A?displayProperty=nameWithType> do konwersji <xref:Windows.Storage.Streams.IRandomAccessStream> nie ogranicza przekonwertowanego strumienia .NET Framework, aby można było go odczytać. Jest również zapisywalny.

## <a name="example-convert-windows-runtime-random-access-to-net-framework-stream"></a>Przykład: konwertowanie środowisko wykonawcze systemu Windows dostęp losowy do strumienia .NET Framework
Aby przekonwertować strumień środowisko wykonawcze systemu Windows dostęp losowy do strumienia .NET Framework, użyj <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A?displayProperty=nameWithType> metody.

Poniższy przykład kodu wyświetla komunikat, aby wybrać plik, otwiera go z środowisko wykonawcze systemu Windows interfejsów API, a następnie konwertuje go na strumień .NET Framework. Odczytuje strumień i wyprowadza go do bloku tekstu. Zazwyczaj można manipulować strumieniem za pomocą interfejsów API .NET Framework, zanim zostaną one wprowadzone.

Aby uruchomić ten przykład, należy utworzyć aplikację XAML platformy UWP, która zawiera blok tekstu o nazwie `TextBlock1` i przycisk o nazwie  `Button1` . Skojarz zdarzenie kliknięcia przycisku z `button1_Click` metodą pokazaną w przykładzie.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage1.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage1.xaml.vb)]

## <a name="convert-from-a-net-framework-to-a-windows-runtime-stream"></a>Konwertowanie .NET Framework na strumień środowisko wykonawcze systemu Windows
Aby przekonwertować strumień .NET Framework do strumienia środowisko wykonawcze systemu Windows, użyj jednej z następujących <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType> metod:

- <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A?displayProperty=nameWithType> Konwertuje zarządzany strumień w programie .NET dla aplikacji platformy UWP na strumień wejściowy w środowisko wykonawcze systemu Windows.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsOutputStream%2A?displayProperty=nameWithType> Konwertuje zarządzany strumień w programie .NET dla aplikacji platformy UWP na strumień danych wyjściowych w środowisko wykonawcze systemu Windows.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream%2A?displayProperty=nameWithType> Konwertuje zarządzany strumień w programie .NET dla aplikacji platformy UWP na strumień dostępu swobodnego, który środowisko wykonawcze systemu Windows może wykorzystać do odczytu lub zapisu.

Podczas konwertowania strumienia .NET Framework do strumienia środowisko wykonawcze systemu Windows możliwości przekonwertowanego strumienia zależą od oryginalnego strumienia. Na przykład, jeśli oryginalny strumień obsługuje odczytywanie i zapisywanie, a wywołanie <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A?displayProperty=nameWithType> do konwersji strumienia, zwracanym typem jest `IRandomAccessStream` . `IRandomAccessStream` implementuje `IInputStream` i `IOutputStream` obsługuje odczytywanie i zapisywanie.

Strumienie .NET Framework nie obsługują klonowania, nawet po konwersji. W przypadku przekonwertowania strumienia .NET Framework na strumień środowisko wykonawcze systemu Windows i wywołanie <xref:Windows.Storage.Streams.InMemoryRandomAccessStream.GetInputStreamAt%2A> lub <xref:Windows.Storage.Streams.IRandomAccessStream.GetOutputStreamAt%2A> , które wywołuje <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> lub jeśli wywołasz <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> bezpośrednio, wystąpi wyjątek.

## <a name="example-convert-net-framework-to-windows-runtime-random-access-stream"></a>Przykład: konwertowanie .NET Framework na środowisko wykonawcze systemu Windows strumień dostępu swobodnego

Aby przekonwertować strumień .NET Framework do strumienia środowisko wykonawcze systemu Windows dostępu swobodnego, użyj <xref:System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream%2A> metody, jak pokazano w następującym przykładzie:

> [!IMPORTANT]
> Upewnij się, że używany strumień .NET Framework obsługuje wyszukiwanie, lub skopiuj go do strumienia, który wykonuje. <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType>Aby to określić, można użyć właściwości.

Aby uruchomić ten przykład, należy utworzyć aplikację XAML platformy UWP, która jest przeznaczona dla .NET Framework 4.5.1 i zawiera blok tekstu o nazwie `TextBlock2` i przycisk o nazwie `Button2` . Skojarz zdarzenie kliknięcia przycisku z `button2_Click` metodą pokazaną w przykładzie.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage2.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage2.xaml.vb)]

## <a name="see-also"></a>Zobacz też

- [Szybki Start: odczytywanie i zapisywanie pliku (Windows)](/previous-versions/windows/apps/hh464978(v=win.10))  
- [Omówienie programu .NET dla aplikacji do sklepu Windows](/previous-versions/windows/apps/br230302(v=vs.140))  
- [Interfejsy API platformy .NET dla aplikacji do sklepu Windows](/previous-versions/br230232(v=vs.120))
