---
title: Interpretowanie kodów błędów zwróconych przez program wsatConfig.exe
ms.date: 03/30/2017
ms.assetid: ab65f22b-0d69-4c21-9aaf-74acef0ca102
ms.openlocfilehash: c5f423f5054a3a80bc0c730444ca9e90c203e288
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262752"
---
# <a name="interpreting-error-codes-returned-by-wsatconfigexe"></a>Interpretowanie kodów błędów zwróconych przez program wsatConfig.exe

W tym temacie wymieniono wszystkie kody błędów wygenerowane przez narzędzie konfiguracji WS-AtomicTransaction (wsatConfig.exe) i zalecane akcje do wykonania.  
  
## <a name="list-of-error-codes"></a>Lista kodów błędów  
  
|Kod błędu|Opis|Zalecana akcja do wykonania|  
|----------------|-----------------|------------------------------------|  
|0|Operacja zakończyła się pomyślnie|Brak|  
|1|Nieoczekiwany błąd|Skontaktuj się z firmą Microsoft|  
|2|Wystąpił nieoczekiwany błąd podczas próby skontaktowania się z koordynatorem MSDTC w celu pobrania jego ustawień zabezpieczeń.|Upewnij się, że usługa MSDTC nie jest wyłączona, i Rozwiąż wszystkie problemy wymienione w zwróconym wyjątku.|  
|3|Konto, na którym uruchomiono WsatConfig.exe, nie miało wystarczających uprawnień do odczytu ustawień zabezpieczeń sieci.|Wykonaj WsatConfig.exe w ramach konta użytkownika administratora.|  
|4|Przed włączeniem obsługi WS-AT Włącz opcję "dostęp do sieci usługi MSDTC".|Włącz opcję "dostęp do usługi Network DTC" dla usługi MSDTC i ponownie uruchom narzędzie.|  
|5|Wprowadzony port jest poza zakresem. Wartość musi należeć do zakresu od 1 do 65535.|Popraw `-port:<portNum>`<br /><br /> Opcja wiersza polecenia określona w komunikacie o błędzie.|  
|6|W wierszu polecenia określono nieprawidłowy certyfikat punktu końcowego.  Nie można znaleźć certyfikatu lub nie przeszedł weryfikacji.|Popraw `-endpointCert` opcję wiersza polecenia. Upewnij się, że certyfikat ma klucz prywatny, który jest przeznaczony do użycia zarówno w rozszerzenie, jak i ServerAuthentication, jest instalowany w magazynie certyfikatów LocalMachine\MY i jest w pełni zaufany.|  
|7|W wierszu polecenia określono nieprawidłowy certyfikat konta.|Popraw `-accountsCerts` opcję wiersza polecenia. Określony certyfikat jest nieprawidłowo określony lub nie można go znaleźć.|  
|8|Określono domyślny limit czasu poza zakresem od 1 do 3600 sekund.|Wprowadź poprawną domyślną wartość limitu czasu zgodnie z podaną wartością.|  
|10|Wystąpił nieoczekiwany błąd podczas próby uzyskania dostępu do rejestru.|Sprawdź komunikat o błędzie i kod błędu dla elementów do wykonania akcji|  
|11|Nie można zapisać do rejestru.|Upewnij się, że klucz wymieniony w komunikacie o błędzie jest w stanie obsługiwać dostęp do rejestru z konta WsatConfig.exe zostało wykonane w ramach.|  
|12|Wystąpił nieoczekiwany błąd podczas próby uzyskania dostępu do magazynu certyfikatów.|Użyj kodu błędu zwróconego do mapowania na odpowiedni błąd systemu.|  
|13|Konfiguracja http.sys nie powiodła się. Nie można utworzyć nowej rezerwacji portu HTTPS dla usługi MSDTC.|Użyj kodu błędu zwróconego do mapowania na odpowiedni błąd systemu.|  
|14|Konfiguracja http.sys nie powiodła się. Nie można usunąć poprzedniej rezerwacji portu HTTPS dla usługi MSDTC.|Użyj kodu błędu zwróconego do mapowania na odpowiedni błąd systemu.|  
|15|Konfiguracja http.sys nie powiodła się. Poprzednia rezerwacja portu HTTPS już istnieje dla określonego portu.|Inna aplikacja już przejmuje własność określonego portu. Zmień na inny port lub Odinstaluj lub ponownie skonfiguruj bieżącą aplikację.|  
|16|Konfiguracja http.sys nie powiodła się. Nie można powiązać określonego certyfikatu z portem.|Użyj kodu błędu zwróconego w komunikacie o błędzie, aby zamapować na odpowiedni błąd systemu|  
|17|Konfiguracja http.sys nie powiodła się. Nie można usunąć powiązania certyfikatu SSL z poprzedniego portu.|Użyj kodu błędu zwróconego w komunikacie o błędzie, aby zamapować na odpowiedni błąd systemu. W razie potrzeby użyj httpcfg.exe lub netsh.exe, aby usunąć błędne rezerwacje portów.|  
|18|Konfiguracja http.sys nie powiodła się. Nie można powiązać określonego certyfikatu z portem, ponieważ poprzednie powiązanie SSL już istnieje.|Inna aplikacja już przejmuje własność określonego portu. Zmień na inny port lub Odinstaluj lub ponownie skonfiguruj bieżącą aplikację.|  
|19|Ponowne uruchamianie usługi MSDTC nie powiodło się|Jeśli to konieczne, należy ręcznie ponownie uruchomić usługę MSDTC. Jeśli problem będzie się powtarzać, skontaktuj się z firmą Microsoft.|  
|20|Program WinFX nie jest zainstalowany na maszynie zdalnej lub nie został poprawnie zainstalowany.|Zainstaluj program WinFX na komputerze.|  
|21|Konfiguracja zdalna nie powiodła się z powodu przekroczenia limitu czasu operacji.|Wywołanie konfiguracji usługi WS-AT na maszynie zdalnej powinno trwać dłużej niż 90 sekund.|  
|22|Program WinFX nie jest zainstalowany na maszynie zdalnej lub nie został poprawnie zainstalowany.|Zainstaluj program WinFX na komputerze.|  
|23|Konfiguracja zdalna nie powiodła się z powodu wyjątku na maszynie zdalnej.|Sprawdź komunikat o błędzie dla elementów z możliwością działania|  
|26|Do WsatConfig.exe przekazano nieprawidłowy argument.|Sprawdź błędy w wierszu polecenia.|  
|27|`-accounts`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `accounts` opcję wiersza polecenia, aby prawidłowo określić konto użytkownika.|  
|28|`-network`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `-network` opcję wiersza polecenia, aby poprawnie określić wartość "Enable" lub "Disable".|  
|29|`-maxTimeout`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `-maxTimeout` opcję wiersza polecenia zgodnie z opisem.|  
|30|`-timeout`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `-timeout` opcję wiersza polecenia zgodnie z opisem.|  
|31|`-traceLevel`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `-traceLevel` opcję wiersza polecenia, aby określić prawidłową wartość z następujących wartości:<br /><br /> -Wył.<br />-Błąd<br />-Krytyczny<br />-Ostrzeżenie<br />-Informacje<br />-Verbose<br />-Wszystkie|  
|32|`-traceActivity`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `-traceActivity` opcję wiersza polecenia, określając wartość "Włącz" lub "Wyłącz".|  
|33|`-traceProp`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `-traceProp` opcję wiersza polecenia, określając wartość "Włącz" lub "Wyłącz".|  
|34|`-tracePII`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `-tracePII` opcję wiersza polecenia, określając wartość "Włącz" lub "Wyłącz".|  
|37|WsatConfig.exe nie mógł określić dokładnego certyfikatu komputera. Może się tak zdarzyć, gdy istnieje więcej niż jeden kandydat lub jeśli nie istnieje.|Określ odcisk palca certyfikatu lub parę Issuer\SubjectName, aby poprawnie zidentyfikować dokładny certyfikat do skonfigurowania.|  
|38|Proces lub użytkownik nie ma wystarczających uprawnień, aby zmienić konfigurację zapory.|Wykonaj WsatConfig.exe w ramach konta użytkownika administratora.|  
|39|WsatConfig.exe napotkał błąd podczas aktualizowania konfiguracji zapory.|Sprawdź komunikat o błędzie dla elementów do wykonania.|  
|40|WsatConfig.exe nie jest w stanie udzielić dostępu do odczytu usługi MSDTC do pliku klucza prywatnego certyfikatu|Wykonaj WsatConfig.exe w ramach konta użytkownika administratora.|  
|41|Nie można znaleźć instalacji programu WinFX lub znaleziona wersja nie jest zgodna z możliwościami konfiguracji narzędzia.|Upewnij się, że model WinFX jest prawidłowo zainstalowany i użyj narzędzia WsatConfig.exe dołączonego do tej wersji programu WinFX, aby skonfigurować usługę WS-AT.|  
|42|Argument został określony więcej niż raz w wierszu polecenia.|Po wykonaniu WsatConfig.exe należy określić tylko jeden argument.|  
|43|Nie można zaktualizować ustawień WS-AT WsatConfig.exe, jeśli Usługa WS-AT nie jest włączona.|Określ `-network:enable` jako dodatkowy argument wiersza polecenia.|  
|44|Brak wymaganej poprawki i Usługa WS-AT nie może zostać skonfigurowana do momentu zainstalowania poprawki.|Zobacz informacje o wersji programu WinFX, aby uzyskać instrukcje dotyczące instalowania wymaganej poprawki.|  
|45|`-virtualServer`Opcja wiersza polecenia jest nieprawidłowa.|Popraw `-virtualServer` opcję wiersza polecenia, określając nazwę sieciową zasobu klastra, w którym ma zostać skonfigurowana konfiguracja.|  
|46|Wystąpił nieoczekiwany błąd podczas próby uruchomienia sesji śledzenia ETW|Użyj kodu błędu zwróconego do mapowania na odpowiedni błąd systemu.|  
|47|Proces lub użytkownik nie ma wystarczających uprawnień, aby włączyć sesję śledzenia ETW.|Wykonaj WsatConfig.exe w ramach konta użytkownika administratora.|  
|48|Wystąpił nieoczekiwany błąd podczas próby uruchomienia sesji śledzenia ETW.|Skontaktuj się z firmą Microsoft.|  
|49|Nie można utworzyć nowego pliku dziennika z powodu niewystarczającej ilości miejsca na dysku% SystemDrive%|Upewnij się, że dysk% systemdrive% ma wystarczającą ilość miejsca na plik dziennika.|  
|51|Wystąpił nieoczekiwany błąd podczas próby uruchomienia sesji śledzenia ETW.|Skontaktuj się z firmą Microsoft.|  
|52|Wystąpił nieoczekiwany błąd podczas próby uruchomienia sesji śledzenia ETW.|Skontaktuj się z firmą Microsoft.|  
|53|Wykonanie kopii zapasowej poprzedniego pliku dziennika sesji ETW nie powiodło się.|Upewnij się, że dysk% systemdrive% ma wystarczającą ilość miejsca na plik dziennika i kopię zapasową poprzedniego pliku dziennika (jeśli istnieje). Jeśli to konieczne, należy ręcznie usunąć poprzedni plik dziennika.|  
|55|Wystąpił nieoczekiwany błąd podczas próby uruchomienia sesji śledzenia ETW.|Skontaktuj się z firmą Microsoft.|  
|56|Wystąpił nieoczekiwany błąd podczas próby uruchomienia sesji śledzenia ETW.|Skontaktuj się z firmą Microsoft.|  
  
## <a name="see-also"></a>Zobacz też

- [Narzędzie do konfiguracji elementu WS-AtomicTransaction (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
