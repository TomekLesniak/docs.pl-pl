---
title: Rozpoczynanie pracy z usługą Azure File Storage przy użyciu języka F#
description: Usługa Magazyn plików Azure umożliwia przechowywanie plików danych w chmurze oraz instalowanie udziału plików w chmurze z maszyny wirtualnej platformy Azure lub z aplikacji lokalnych działających w systemie Windows.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: dd19b156e73774f4eca63afd3f4c10a4a7b8d46c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100129"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Rozpoczynanie pracy z usługą Azure File Storage przy użyciu języka F\#

Azure File Storage to usługa, która umożliwia korzystanie z udziałów plików w chmurze przy użyciu standardowego [protokołu bloku komunikatów serwera (SMB)](/windows/win32/fileio/microsoft-smb-protocol-and-cifs-protocol-overview). Obsługiwane są wersje 2.1 i 3.0 protokołu SMB. W usłudze Magazyn plików Azure można migrować starsze aplikacje korzystające z udziałów plików na platformę Azure szybko i bez kosztownych modyfikacji oprogramowania. Aplikacje uruchomione na maszynach wirtualnych lub w ramach usług w chmurze platformy Azure, a także na klientach lokalnych mogą instalować udziały plików w chmurze tak samo jak aplikacja na komputerze instalująca typowy udział SMB. Dowolna liczba składników aplikacji może następnie równocześnie zainstalować udział Magazynu plików i uzyskiwać do niego dostęp.

Aby zapoznać się z omówieniem koncepcyjnym usługi File Storage, zobacz [Przewodnik po platformie .NET dotyczący usługi File Storage](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Wymagania wstępne

Aby skorzystać z tego przewodnika, musisz najpierw [utworzyć konto usługi Azure Storage](/azure/storage/storage-create-storage-account).
Wymagany jest również klucz dostępu do magazynu dla tego konta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Utwórz skrypt języka F # i zacznij F# Interactive

Przykłady w tym artykule mogą być używane w przypadku aplikacji F # lub skryptu języka F #. Aby utworzyć skrypt języka F #, Utwórz plik z `.fsx` rozszerzeniem, na przykład `files.fsx` w środowisku deweloperskim języka f #.

Następnie należy użyć [Menedżera pakietów](package-management.md) , takiego jak [Paket](https://fsprojects.github.io/Paket/) lub [NuGet](https://www.nuget.org/) , aby zainstalować `WindowsAzure.Storage` pakiet i odwołanie `WindowsAzure.Storage.dll` w skrypcie przy użyciu `#r` dyrektywy.

### <a name="add-namespace-declarations"></a>Dodawanie deklaracji przestrzeni nazw

Dodaj następujące instrukcje `open` na początku pliku `files.fsx`:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Uzyskiwanie parametrów połączenia

W tym samouczku będą potrzebne parametry połączenia usługi Azure Storage. Aby uzyskać więcej informacji dotyczących parametrów połączenia, zobacz [Konfigurowanie parametrów połączenia magazynu](/azure/storage/storage-configure-connection-string).

Na potrzeby samouczka wprowadzisz w skrypcie parametry połączenia, takie jak:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Nie jest to jednak **zalecane** w przypadku rzeczywistych projektów. Klucz konta magazynu jest podobny do hasła głównego konta magazynu. Zawsze chroń klucz konta magazynu. Nie udostępniaj go innym użytkownikom, nie koduj go trwale ani nie zapisuj w zwykłym pliku tekstowym, do którego mają dostęp inne osoby. Możesz ponownie wygenerować klucz przy użyciu Azure Portal, jeśli uważasz, że jego zabezpieczenia mogły zostać naruszone.

W przypadku prawdziwych aplikacji najlepszym sposobem obsługi parametrów połączenia magazynu jest w pliku konfiguracji. Aby pobrać parametry połączenia z pliku konfiguracji, można to zrobić:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Użycie programu Azure Configuration Manager jest opcjonalne. Można również użyć interfejsu API, takiego jak `ConfigurationManager` typ .NET Framework.

### <a name="parse-the-connection-string"></a>Analizowanie parametrów połączenia

Aby przeanalizować parametry połączenia, użyj:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Spowoduje to zwrócenie elementu `CloudStorageAccount` .

### <a name="create-the-file-service-client"></a>Tworzenie klienta usługi plików

`CloudFileClient`Typ pozwala programistycznie używać plików przechowywanych w magazynie plików. Oto jeden ze sposobów tworzenia klienta usługi:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Teraz możesz przystąpić do pisania kodu, który odczytuje dane z magazynu plików i zapisuje je w nim.

## <a name="create-a-file-share"></a>Tworzenie udziału plików

Ten przykład pokazuje, jak utworzyć udział plików, jeśli jeszcze nie istnieje:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Tworzenie katalogu głównego i podkatalogu

W tym miejscu otrzymujesz katalog główny i uzyskasz podkatalog w katalogu głównym. Należy utworzyć obie, jeśli jeszcze nie istnieją.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Przekaż tekst jako plik

Ten przykład pokazuje, jak przekazać tekst jako plik.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Pobierz plik do lokalnej kopii pliku

W tym miejscu pobierasz utworzony plik, dołączając zawartość do pliku lokalnego.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Ustawianie maksymalnego rozmiaru udziału plików

W poniższym przykładzie pokazano, jak sprawdzić bieżące użycie udziału oraz jak ustawić limit przydziału w udziale. `FetchAttributes` musi być wywołana, aby wypełnić udział `Properties` i `SetProperties` propagowanie lokalnych zmian do usługi Azure File Storage.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generowanie sygnatury dostępu współdzielonego dla pliku lub udziału plików

Można wygenerować sygnaturę dostępu współdzielonego (SAS) dla udziału plików lub dla pojedynczego pliku. Można też utworzyć zasady dostępu współdzielonego w udziale plików na potrzeby zarządzania sygnaturami dostępu współdzielonego. Utworzenie zasad dostępu współdzielonego jest zalecane, ponieważ umożliwia cofnięcie sygnatur w przypadku zagrożenia bezpieczeństwa.

W tym miejscu można utworzyć zasady dostępu współdzielonego w udziale, a następnie użyć tych zasad w celu zapewnienia ograniczeń dla SAS dla pliku w udziale.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Aby uzyskać więcej informacji na temat tworzenia i używania sygnatur dostępu współdzielonego, zobacz [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) (Używanie sygnatur dostępu współdzielonego (SAS)) oraz [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2) (Tworzenie i używanie sygnatury dostępu współdzielonego w Magazynie obiektów Blob).

### <a name="copy-files"></a>Kopiowanie plików

Plik można skopiować do innego pliku lub do obiektu BLOB lub do pliku. Jeśli kopiujesz obiekt BLOB do pliku lub pliku do obiektu BLOB, *musisz* użyć sygnatury dostępu współdzielonego do uwierzytelnienia obiektu źródłowego, nawet jeśli kopiujesz w ramach tego samego konta magazynu.

### <a name="copy-a-file-to-another-file"></a>Kopiowanie pliku do innego pliku

W tym miejscu skopiujesz plik do innego pliku w tym samym udziale. Ponieważ ta operacja kopiowania jest wykonywana w ramach tego samego konta magazynu, można użyć uwierzytelniania przy użyciu klucza wspólnego.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Kopiowanie pliku do obiektu blob

Tutaj utworzysz plik i skopiujesz go do obiektu BLOB w ramach tego samego konta magazynu. Tworzysz sygnaturę dostępu współdzielonego dla pliku źródłowego, którego usługa używa do uwierzytelniania w pliku źródłowym podczas operacji kopiowania.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

W ten sam sposób można skopiować obiekt blob do pliku. Jeśli obiekt źródłowy jest obiektem blob, utwórz sygnaturę dostępu współdzielonego w celu uwierzytelniania dostępu do tego obiektu blob podczas operacji kopiowania.

## <a name="troubleshooting-file-storage-using-metrics"></a>Rozwiązywanie problemów z usługą Magazyn plików przy użyciu metryk

Analityka magazynu platformy Azure obsługuje metryki dla usługi File Storage. Dane metryk umożliwiają śledzenie żądań i diagnozowanie problemów.

Metryki dla usługi File Storage można włączyć z poziomu [Azure Portal](https://portal.azure.com)lub można wykonać te czynności w języku F # podobnej do tego:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Następne kroki

Aby uzyskać więcej informacji na temat usługi Azure File Storage, zobacz te linki.

### <a name="conceptual-articles-and-videos"></a>Artykuły koncepcyjne i filmy

- [Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/) (Azure File Storage: płynnie działający system plików SMB w chmurze dla systemów Windows i Linux)
- [Jak korzystać z usługi Azure File Storage z systemem Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Narzędzia dostępne dla usługi Magazyn plików

- [Używanie programu Azure PowerShell z usługą Azure Storage](/azure/storage/storage-powershell-guide-full)
- [How to use AzCopy with Microsoft Azure Storage (Jak używać narzędzia AzCopy z usługą Magazyn Microsoft Azure)](/azure/storage/storage-use-azcopy)
- [Tworzenie, pobieranie i wyświetlanie listy obiektów BLOB za pomocą interfejsu wiersza polecenia platformy Azure](/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a>Dokumentacja

- [Dokumentacja biblioteki klienta usługi Storage dla platformy .NET](/dotnet/api/overview/azure/storage)
- [Dokumentacja interfejsu API REST usługi plików](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Wpisy na blogach

- [Azure File storage is now generally available (Usługa Magazyn plików Azure została udostępniona publicznie)](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Inside Azure File Storage](https://azure.microsoft.com/blog/inside-azure-file-storage/) (Za kulisami usługi Azure File Storage)
- [Introducing Microsoft Azure File Service](/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service) (Wprowadzenie do usługi plików platformy Microsoft Azure)
- [Persisting connections to Microsoft Azure Files (Utrwalanie połączeń z plikami na platformie Microsoft Azure)](/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
