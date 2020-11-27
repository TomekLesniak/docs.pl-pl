---
title: Storeadm.exe (Narzędzie wydzielonej pamięci masowej)
description: Przeczytaj informacje o Storeadm.exe, narzędziu do magazynowania izolowanego. To narzędzie wyświetla lub usuwa wszystkie istniejące magazyny dla bieżącego użytkownika.
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
ms.openlocfilehash: 974f3c464ff686a486657d08e77c97299cc94732
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283838"
---
# <a name="storeadmexe-isolated-storage-tool"></a>Storeadm.exe (Narzędzie wydzielonej pamięci masowej)

Narzędzie Isolated Storage obsługujące izolowane magazyny wyświetla lub usuwa wszystkie istniejące magazyny bieżącego użytkownika.  
  
 To narzędzie jest instalowane automatycznie z programem Visual Studio. Aby uruchomić narzędzie, użyj wiersz polecenia dla deweloperów dla programu Visual Studio (lub wiersza polecenia programu Visual Studio w systemie Windows 7). Aby uzyskać więcej informacji, zobacz [wiersza polecenia](developer-command-prompt-for-vs.md).  
  
 W wierszu polecenia wpisz następujące polecenie:  
  
## <a name="syntax"></a>Składnia  
  
```console  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a>Parametry  
  
|Opcja|Opis|  
|------------|-----------------|  
|**/h**[**ELP**]|Wyświetla składnię polecenia i opcje narzędzia.|  
|**/list**|Wyświetla wszystkie istniejące magazyny bieżącego użytkownika. W tym magazyny dla wszystkich aplikacji lub zespołów wykonanych przez tego użytkownika.|  
|**/Machine**|Wybiera magazyn komputera. Użyj tej opcji z opcją **/list** lub **/Remove** , aby określić, że akcja ma być stosowana do magazynu komputera.<br /><br /> Nowość w programie .NET Framework 2.0|  
|**spowoduje**|Określa tryb cichy; pomija informacyjne dane wyjściowe, tak aby były wyświetlane tylko komunikaty o błędach.|  
|**/Remove**|Trwale usuwa wszystkie istniejące magazyny bieżącego użytkownika.|  
|**/roaming**|Wybiera mobilny magazyn. Użyj tej opcji z opcjami **/list** lub **/Remove** , aby określić, że akcja ma być stosowana do magazynu mobilnego.|  
|**/?**|Wyświetla składnię polecenia i opcje narzędzia.|  
  
## <a name="remarks"></a>Uwagi  

 Uruchamianie Storeadm.exe z wiersza polecenia bez określenia opcji wyświetla składnię i opcje narzędzia.  
  
 Opcje **/list** i **/Remove** są zwykle używane pojedynczo. Jednak jeśli określono dwie lub więcej opcji, zostaną one wykonane w kolejności, w jakiej występują w wierszu polecenia.  
  
 Aplikacje można zapisać do jednego z dwóch magazynów użytkownika lub do magazynu komputera:  
  
- Magazyn lokalny istnieje w lokalizacji, która nie jest przenoszona (w systemie Windows 2000 i nowszych) nawet wtedy, gdy dla użytkownika włączono funkcję mobilnego dostępu do danych użytkownika.  
  
- Magazyn mobilny istnieje w lokalizacji, która może przechować, ale tylko wtedy, gdy roaming jest włączony dla użytkownika za pośrednictwem administracji systemu Windows NT.  
  
- Magazyn komputera jest wspólny dla wszystkich użytkowników komputera i jest przechowywany we wspólnym katalogu na tym komputerze.  
  
    > [!NOTE]
    > Magazyn komputera jest nowy w programie .NET Framework w wersji 2.0.  
  
 To, czy roaming jest faktycznie włączony dla użytkownika, nie wpływa na administrację Storeadm.exe. Uruchomienie narzędzia bez żadnych opcji zastosuje wszystkie akcje do magazynu lokalnego. Uruchomienie narzędzia z opcją **/roaming** dotyczy wszystkich akcji w sklepie, który ma możliwość przeroamingu. Uruchomienie narzędzia z opcją **/Machine** powoduje zastosowanie wszystkich akcji do magazynu komputera.  
  
## <a name="see-also"></a>Zobacz też

- [Narzędzia](index.md)
- [Magazyn izolowany](../../standard/io/isolated-storage.md)
- [Wiersze poleceń](developer-command-prompt-for-vs.md)
