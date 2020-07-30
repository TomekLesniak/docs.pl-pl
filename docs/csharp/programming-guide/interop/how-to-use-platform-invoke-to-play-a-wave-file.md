---
title: Jak używać wywołania platformy do odtwarzania pliku WAV — Przewodnik programowania w języku C#
description: Ten przykładowy kod w języku C# ilustruje sposób używania usług wywołania platformy do odtwarzania pliku dźwiękowego WAV w systemie operacyjnym Windows.
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: b30cb08e2dcde0eb85e8d88a690ae24bf7ae7f22
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302987"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a><span data-ttu-id="48c9a-103">Jak używać wywołania platformy do odtwarzania pliku WAV (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="48c9a-103">How to use platform invoke to play a WAV file (C# Programming Guide)</span></span>

<span data-ttu-id="48c9a-104">Poniższy przykład kodu w języku C# ilustruje sposób używania usług wywołania platformy do odtwarzania pliku dźwiękowego WAV w systemie operacyjnym Windows.</span><span class="sxs-lookup"><span data-stu-id="48c9a-104">The following C# code example illustrates how to use platform invoke services to play a WAV sound file on the Windows operating system.</span></span>

## <a name="example"></a><span data-ttu-id="48c9a-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="48c9a-105">Example</span></span>

<span data-ttu-id="48c9a-106">Ten przykładowy kod używa <xref:System.Runtime.InteropServices.DllImportAttribute> do importowania `winmm.dll` `PlaySound` punktu wejścia metody jako `Form1 PlaySound()` .</span><span class="sxs-lookup"><span data-stu-id="48c9a-106">This example code uses <xref:System.Runtime.InteropServices.DllImportAttribute> to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="48c9a-107">Przykład ma prosty formularz systemu Windows z przyciskiem.</span><span class="sxs-lookup"><span data-stu-id="48c9a-107">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="48c9a-108">Kliknięcie tego przycisku powoduje otwarcie standardowego okna dialogowego systemu Windows, <xref:System.Windows.Forms.OpenFileDialog> w którym można otworzyć plik do odtworzenia.</span><span class="sxs-lookup"><span data-stu-id="48c9a-108">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="48c9a-109">Po wybraniu pliku Wave jest on odtwarzany przy użyciu `PlaySound()` metody biblioteki *winmm.dll* .</span><span class="sxs-lookup"><span data-stu-id="48c9a-109">When a wave file is selected, it is played by using the `PlaySound()` method of the *winmm.dll* library.</span></span> <span data-ttu-id="48c9a-110">Aby uzyskać więcej informacji na temat tej metody, zobacz [Używanie funkcji PlaySound z plikami Wave-audio](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span><span class="sxs-lookup"><span data-stu-id="48c9a-110">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="48c9a-111">Przeglądaj i wybierz plik z rozszerzeniem WAV, a następnie kliknij przycisk **Otwórz** , aby odtworzyć plik Wave przy użyciu wywołania platformy.</span><span class="sxs-lookup"><span data-stu-id="48c9a-111">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="48c9a-112">Pole tekstowe zawiera pełną ścieżkę wybranego pliku.</span><span class="sxs-lookup"><span data-stu-id="48c9a-112">A text box shows the full path of the file selected.</span></span>

<span data-ttu-id="48c9a-113">Okno dialogowe **otwieranie plików** jest filtrowane w celu wyświetlania tylko plików o rozszerzeniu WAV z wykorzystaniem ustawień filtru:</span><span class="sxs-lookup"><span data-stu-id="48c9a-113">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a><span data-ttu-id="48c9a-114">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="48c9a-114">Compiling the code</span></span>

1. <span data-ttu-id="48c9a-115">Utwórz nowy projekt aplikacji w języku C# Windows Forms w programie Visual Studio i nadaj mu nazwę **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="48c9a-115">Create a new C# Windows Forms Application project in Visual Studio and name it **WinSound**.</span></span>

2. <span data-ttu-id="48c9a-116">Skopiuj powyższy kod i wklej go do zawartości pliku *Form1.cs* .</span><span class="sxs-lookup"><span data-stu-id="48c9a-116">Copy the code above, and paste it over the contents of the *Form1.cs* file.</span></span>

3. <span data-ttu-id="48c9a-117">Skopiuj poniższy kod i wklej go w pliku *Form1.Designer.cs* , w `InitializeComponent()` metodzie, po dowolnym istniejącym kodzie.</span><span class="sxs-lookup"><span data-stu-id="48c9a-117">Copy the following code, and paste it in the *Form1.Designer.cs* file, in the `InitializeComponent()` method, after any existing code.</span></span>

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. <span data-ttu-id="48c9a-118">Kompiluj i uruchamiaj kod.</span><span class="sxs-lookup"><span data-stu-id="48c9a-118">Compile and run the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="48c9a-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="48c9a-119">See also</span></span>

- [<span data-ttu-id="48c9a-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="48c9a-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="48c9a-121">Przegląd współdziałania</span><span class="sxs-lookup"><span data-stu-id="48c9a-121">Interoperability Overview</span></span>](interoperability-overview.md)
- [<span data-ttu-id="48c9a-122">Bliższe spojrzenie na wywołanie platformy</span><span class="sxs-lookup"><span data-stu-id="48c9a-122">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="48c9a-123">Organizowanie danych w wywołaniu platformy</span><span class="sxs-lookup"><span data-stu-id="48c9a-123">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
