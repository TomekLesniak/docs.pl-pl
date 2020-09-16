---
ms.openlocfilehash: 12ba3bd3c9e9e00b88cab0e568a1ce0f4f8bbb05
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606565"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a><span data-ttu-id="fe616-101">CspParameters. ParentWindowHandle teraz oczekuje wartości HWND</span><span class="sxs-lookup"><span data-stu-id="fe616-101">CspParameters.ParentWindowHandle now expects HWND value</span></span>

#### <a name="details"></a><span data-ttu-id="fe616-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="fe616-102">Details</span></span>

<span data-ttu-id="fe616-103"><xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>Wartość wprowadzona w .NET Framework 2,0 umożliwia aplikacji zarejestrowanie wartości uchwytu okna nadrzędnego w taki sposób, że każdy interfejs użytkownika wymagany do uzyskania dostępu do klucza (na przykład monitu o podanie numeru PIN lub okna dialogowego zgody) otwiera się jako modalny element podrzędny do określonego okna. Począwszy od aplikacji przeznaczonych dla .NET Framework 4,7, aplikacja Windows Forms może ustawić <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> Właściwość z kodem podobnym do poniższego:</span><span class="sxs-lookup"><span data-stu-id="fe616-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> value, introduced in .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or consent dialog) opens as a modal child to the specified window.Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="fe616-104">W poprzednich wersjach .NET Framework oczekiwano, że wartość będzie <xref:System.IntPtr?displayProperty=fullName> reprezentować lokalizację w pamięci, w której znajduje się wartość [HWND](/windows/desktop/WinProg/windows-data-types#HWND) .</span><span class="sxs-lookup"><span data-stu-id="fe616-104">In previous versions of the .NET Framework, the value was expected to be an <xref:System.IntPtr?displayProperty=fullName> representing a location in memory where the [HWND](/windows/desktop/WinProg/windows-data-types#HWND) value resided.</span></span> <span data-ttu-id="fe616-105">Ustawianie właściwości na postać. Obsługa w systemie Windows 7 i starszych wersjach nie miała znaczenia, ale w systemie Windows 8 i nowszych wersjach jego wynikiem jest &quot; <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> : parametr jest nieprawidłowy.&quot;</span><span class="sxs-lookup"><span data-stu-id="fe616-105">Setting the property to form.Handle on Windows 7 and earlier versions had no effect, but on Windows 8 and later versions, it results in a &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: The parameter is incorrect.&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fe616-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="fe616-106">Suggestion</span></span>

<span data-ttu-id="fe616-107">W przypadku aplikacji przeznaczonych dla .NET Framework 4,7 lub wyższych chcemy zarejestrowanie relacji między oknem nadrzędnym zaleca się użycie formy uproszczonej:</span><span class="sxs-lookup"><span data-stu-id="fe616-107">Applications targeting .NET Framework 4.7 or higher wishing to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="fe616-108">Użytkownicy, którzy zidentyfikowali, że poprawna wartość jest adresem lokalizacji pamięci, która posiadała wartość, `form.Handle` może zrezygnować z zmiany zachowania, ustawiając przełącznik AppContext `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` na `true` :</span><span class="sxs-lookup"><span data-stu-id="fe616-108">Users who had identified that the correct value to pass was the address of a memory location which held the value `form.Handle` can opt out of the behavior change by setting the AppContext switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="fe616-109">Przez programowe ustawianie przełączników zgodności w AppContext, jak wyjaśniono [tutaj](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span><span class="sxs-lookup"><span data-stu-id="fe616-109">By programmatically setting compat switches on the AppContext, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="fe616-110">Dodając następujący wiersz do `<runtime>` sekcji pliku app.config:</span><span class="sxs-lookup"><span data-stu-id="fe616-110">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

<span data-ttu-id="fe616-111">W przypadku użytkowników, którzy chcą zrezygnować z nowego zachowania w środowisku uruchomieniowym .NET Framework 4,7, gdy aplikacja jest ładowana w starszej wersji .NET Framework, można ustawić przełącznik AppContext na `false` .</span><span class="sxs-lookup"><span data-stu-id="fe616-111">Conversely, users who wish to opt in to the new behavior on the .NET Framework 4.7 runtime when the application loads under older .NET Framework versions can set the AppContext switch to `false`.</span></span>

| <span data-ttu-id="fe616-112">Nazwa</span><span class="sxs-lookup"><span data-stu-id="fe616-112">Name</span></span>    | <span data-ttu-id="fe616-113">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe616-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fe616-114">Zakres</span><span class="sxs-lookup"><span data-stu-id="fe616-114">Scope</span></span>   | <span data-ttu-id="fe616-115">Mały</span><span class="sxs-lookup"><span data-stu-id="fe616-115">Minor</span></span>       |
| <span data-ttu-id="fe616-116">Wersja</span><span class="sxs-lookup"><span data-stu-id="fe616-116">Version</span></span> | <span data-ttu-id="fe616-117">4,7</span><span class="sxs-lookup"><span data-stu-id="fe616-117">4.7</span></span>         |
| <span data-ttu-id="fe616-118">Typ</span><span class="sxs-lookup"><span data-stu-id="fe616-118">Type</span></span>    | <span data-ttu-id="fe616-119">Przekierowanie</span><span class="sxs-lookup"><span data-stu-id="fe616-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="fe616-120">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="fe616-120">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>
