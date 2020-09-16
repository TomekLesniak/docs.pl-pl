---
ms.openlocfilehash: 7c4b9faf25853c1c7a546f06c329f6f153eef904
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606666"
---
### <a name="changes-in-path-normalization"></a><span data-ttu-id="04f75-101">Zmiany normalizacji ścieżki</span><span class="sxs-lookup"><span data-stu-id="04f75-101">Changes in path normalization</span></span>

#### <a name="details"></a><span data-ttu-id="04f75-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="04f75-102">Details</span></span>

<span data-ttu-id="04f75-103">Począwszy od aplikacji przeznaczonych dla .NET Framework 4.6.2, sposób, w jaki środowisko uruchomieniowe normalizuje ścieżki, zostało zmienione. Normalizowanie ścieżki polega na zmodyfikowaniu ciągu, który identyfikuje ścieżkę lub plik, tak aby był zgodny z prawidłową ścieżką w docelowym systemie operacyjnym.</span><span class="sxs-lookup"><span data-stu-id="04f75-103">Starting with apps that target the .NET Framework 4.6.2, the way in which the runtime normalizes paths has changed.Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="04f75-104">Normalizacja zazwyczaj obejmuje:</span><span class="sxs-lookup"><span data-stu-id="04f75-104">Normalization typically involves:</span></span>

- <span data-ttu-id="04f75-105">Separatory składników formę kanoniczną działa i katalogów.</span><span class="sxs-lookup"><span data-stu-id="04f75-105">Canonicalizing component and directory separators.</span></span>
- <span data-ttu-id="04f75-106">Zastosowanie bieżącego katalogu do ścieżki względnej.</span><span class="sxs-lookup"><span data-stu-id="04f75-106">Applying the current directory to a relative path.</span></span>
- <span data-ttu-id="04f75-107">Ocenianie katalogu względnego (.) lub katalogu nadrzędnego (..) w ścieżce.</span><span class="sxs-lookup"><span data-stu-id="04f75-107">Evaluating the relative directory (.) or the parent directory (..) in a path.</span></span>
- <span data-ttu-id="04f75-108">Przycinanie określonych znaków.</span><span class="sxs-lookup"><span data-stu-id="04f75-108">Trimming specified characters.</span></span>
<span data-ttu-id="04f75-109">Począwszy od aplikacji przeznaczonych dla .NET Framework 4.6.2, następujące zmiany normalizacji ścieżki są domyślnie włączone:</span><span class="sxs-lookup"><span data-stu-id="04f75-109">Starting with apps that target the .NET Framework 4.6.2, the following changes in path normalization are enabled by default:</span></span>
  - <span data-ttu-id="04f75-110">Środowisko uruchomieniowe odkłada do funkcji [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) systemu operacyjnego, aby znormalizować ścieżki.</span><span class="sxs-lookup"><span data-stu-id="04f75-110">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) function to normalize paths.</span></span>
- <span data-ttu-id="04f75-111">Normalizacja nie obejmuje już przecinania końców segmentów katalogów (takich jak spacja na końcu nazwy katalogu).</span><span class="sxs-lookup"><span data-stu-id="04f75-111">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>
- <span data-ttu-id="04f75-112">Obsługa składni ścieżki urządzenia w pełnym zaufaniu, w tym `\\.\` i dla interfejsów API we/wy plików w mscorlib.dll, `\\?\` .</span><span class="sxs-lookup"><span data-stu-id="04f75-112">Support for device path syntax in full trust, including `\\.\` and, for file I/O APIs in mscorlib.dll, `\\?\`.</span></span>
- <span data-ttu-id="04f75-113">Środowisko uruchomieniowe nie sprawdza poprawności ścieżek składni urządzeń.</span><span class="sxs-lookup"><span data-stu-id="04f75-113">The runtime does not validate device syntax paths.</span></span>
- <span data-ttu-id="04f75-114">Obsługiwane jest użycie składni urządzenia w celu uzyskania dostępu do alternatywnych strumieni danych.</span><span class="sxs-lookup"><span data-stu-id="04f75-114">The use of device syntax to access alternate data streams is supported.</span></span>
<span data-ttu-id="04f75-115">Te zmiany zwiększają wydajność, a jednocześnie umożliwiają uzyskanie dostępu do wcześniej niedostępnych ścieżek.</span><span class="sxs-lookup"><span data-stu-id="04f75-115">These changes improve performance while allowing methods to access previously inaccessible paths.</span></span> <span data-ttu-id="04f75-116">Ta zmiana nie wpłynie na aplikacje, które są przeznaczone dla .NET Framework 4.6.1 i wcześniejszych wersji, ale działają na .NET Framework 4.6.2 lub nowszych.</span><span class="sxs-lookup"><span data-stu-id="04f75-116">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="04f75-117">Sugestia</span><span class="sxs-lookup"><span data-stu-id="04f75-117">Suggestion</span></span>

<span data-ttu-id="04f75-118">Aplikacje przeznaczone dla .NET Framework 4.6.2 lub nowszych mogą zrezygnować z tej zmiany i użyć starszej normalizacji, dodając następujący element do `<runtime>` sekcji pliku konfiguracyjnego aplikacji:</span><span class="sxs-lookup"><span data-stu-id="04f75-118">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

<span data-ttu-id="04f75-119">Aplikacje, które są przeznaczone dla .NET Framework 4.6.1 lub wcześniejszych, ale działają na .NET Framework 4.6.2 lub później, mogą umożliwić zmianę normalizacji ścieżki, dodając następujący wiersz do `<runtime>` sekcji pliku Application. Configuration:</span><span class="sxs-lookup"><span data-stu-id="04f75-119">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| <span data-ttu-id="04f75-120">Nazwa</span><span class="sxs-lookup"><span data-stu-id="04f75-120">Name</span></span>    | <span data-ttu-id="04f75-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="04f75-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="04f75-122">Zakres</span><span class="sxs-lookup"><span data-stu-id="04f75-122">Scope</span></span>   | <span data-ttu-id="04f75-123">Mały</span><span class="sxs-lookup"><span data-stu-id="04f75-123">Minor</span></span>       |
| <span data-ttu-id="04f75-124">Wersja</span><span class="sxs-lookup"><span data-stu-id="04f75-124">Version</span></span> | <span data-ttu-id="04f75-125">4.6.2</span><span class="sxs-lookup"><span data-stu-id="04f75-125">4.6.2</span></span>       |
| <span data-ttu-id="04f75-126">Typ</span><span class="sxs-lookup"><span data-stu-id="04f75-126">Type</span></span>    | <span data-ttu-id="04f75-127">Przekierowanie</span><span class="sxs-lookup"><span data-stu-id="04f75-127">Retargeting</span></span> |
