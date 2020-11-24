---
title: Łączenie statycznych funkcji globalnych
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
ms.openlocfilehash: 691fd50e05cadd3f82196fc6ba5df9bb84a66faa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688747"
---
# <a name="fusion-global-static-functions"></a>Łączenie statycznych funkcji globalnych

W tej sekcji opisano niezarządzane globalne funkcje statyczne używane przez interfejs API Fusion.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [ClearDownloadCache — Funkcja](cleardownloadcache-function.md)  
 Czyści globalną pamięć podręczną zestawów pobranych zestawów.  
  
 [CompareAssemblyIdentity — Funkcja](compareassemblyidentity-function.md)  
 Porównuje dwie tożsamości zestawów, aby określić, czy są one równoważne.  
  
 [CreateApplicationContext — Funkcja](createapplicationcontext-function.md)  
 Tylko do użytku wewnętrznego. (Ta funkcja obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie).  
  
 [CreateAssemblyCache — Funkcja](createassemblycache-function.md)  
 Pobiera wskaźnik do nowego wystąpienia [IAssemblyCache](iassemblycache-interface.md) , które reprezentuje globalną pamięć podręczną zestawów.  
  
 [CreateAssemblyEnum — Funkcja](createassemblyenum-function.md)  
 Pobiera wskaźnik do wystąpienia [IAssemblyEnum](iassemblyenum-interface.md) , które reprezentuje listę obiektów istniejących w określonym zestawie.  
  
 [CreateAssemblyNameObject — Funkcja](createassemblynameobject-function.md)  
 Pobiera wskaźnik do wystąpienia [IAssemblyName](iassemblyname-interface.md) , które reprezentuje unikatową tożsamość zestawu o określonej nazwie.  
  
 [CreateHistoryReader — Funkcja](createhistoryreader-function.md)  
 Tworzy czytelnika historii dla określonego pliku.  
  
 [CreateInstallReferenceEnum — Funkcja](createinstallreferenceenum-function.md)  
 Pobiera wskaźnik do wystąpienia [IInstallReferenceEnum](iinstallreferenceenum-interface.md) , które reprezentuje listę odwołań aplikacji do określonego zestawu.  
  
 [GetAppIdAuthority — Funkcja](getappidauthority-function.md)  
 Pobiera wskaźnik do wystąpienia [IAppIdAuthority —](iappidauthority-interface.md) , które zarządza kluczami dla tożsamości i odwołań aplikacji.  
  
 [GetAssemblyIdentityFromFile — Funkcja](getassemblyidentityfromfile-function.md)  
 Pobiera wskaźnik do `IUnknown` obiektu z określonym `IID` w zestawie w określonej ścieżce pliku.  
  
 [GetCachePath — Funkcja](getcachepath-function.md)  
 Pobiera ścieżkę do buforowanego zestawu przy użyciu określonych flag.  
  
 [GetHistoryFileDirectory — Funkcja](gethistoryfiledirectory-function.md)  
 Pobiera ścieżkę katalogu historii aplikacji.  
  
 [GetIdentityAuthority — Funkcja](getidentityauthority-function.md)  
 Pobiera wskaźnik do wystąpienia [IIdentityAuthority —](iidentityauthority-interface.md) , które zarządza kluczami obiektów kodu.  
  
 [IsFrameworkAssembly — Funkcja](isframeworkassembly-function.md)  
 Pobiera wartość wskazującą, czy określony zestaw jest zarządzany.  
  
 [NukeDownloadedCache — Funkcja](nukedownloadedcache-function.md)  
 Usuwa pamięć podręczną pobierania środowiska uruchomieniowego języka wspólnego.  
  
 [PreBindAssemblyEx — Funkcja](prebindassemblyex-function.md)  
 Pobiera nazwę wyświetlaną dla zestawu.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Interfejsy łączenia](fusion-interfaces.md)  
  
 [Wyliczenia łączenia](fusion-enumerations.md)  
  
 [Łączenie — Struktury](fusion-structures.md)  
  
 [Global Assembly Cache](../../app-domains/gac.md)
