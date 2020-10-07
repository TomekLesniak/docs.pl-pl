---
title: Rozpoczynanie pracy z usługą Azure Blob Storage przy użyciu języka F#
description: Przechowuj dane niestrukturalne w chmurze za pomocą usługi Azure Blob Storage.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 91aec8fc2b57c71ce4ba47d62619912af6c71e59
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756250"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Rozpoczynanie pracy z usługą Azure Blob Storage przy użyciu języka F\#

Magazyn obiektów blob Azure jest usługą służącą do przechowywania danych niestrukturalnych w chmurze w postaci obiektów blob. Magazyn obiektów blob umożliwia przechowywanie dowolnego typu danych tekstowych lub binarnych, takich jak dokumenty, pliki multimedialne lub instalatory aplikacji. Magazyn obiektów blob jest również nazywany magazynem obiektów.

W tym artykule przedstawiono sposób wykonywania typowych zadań za pomocą usługi BLOB Storage. Przykłady są zapisywane przy użyciu języka F # przy użyciu biblioteki klienta usługi Azure Storage dla platformy .NET. Objęte zadaniami obejmują sposób przekazywania, wyświetlania, pobierania i usuwania obiektów BLOB.

Ogólne omówienie usługi BLOB Storage można znaleźć [w przewodniku .NET dla usługi BLOB Storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet).

## <a name="prerequisites"></a>Wymagania wstępne

Aby skorzystać z tego przewodnika, musisz najpierw [utworzyć konto usługi Azure Storage](/azure/storage/common/storage-account-create). Wymagany jest również klucz dostępu do magazynu dla tego konta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Utwórz skrypt języka F # i zacznij F# Interactive

Przykłady w tym artykule mogą być używane w przypadku aplikacji F # lub skryptu języka F #. Aby utworzyć skrypt języka F #, Utwórz plik z `.fsx` rozszerzeniem, na przykład `blobs.fsx` w środowisku deweloperskim języka f #.

Następnie należy użyć [Menedżera pakietów](package-management.md) , takiego jak [Paket](https://fsprojects.github.io/Paket/) lub [NuGet](https://www.nuget.org/) , aby zainstalować `WindowsAzure.Storage` `Microsoft.WindowsAzure.ConfigurationManager` pakiety i odwołania oraz `WindowsAzure.Storage.dll` `Microsoft.WindowsAzure.Configuration.dll` w skrypcie przy użyciu `#r` dyrektywy.

### <a name="add-namespace-declarations"></a>Dodawanie deklaracji przestrzeni nazw

Dodaj następujące instrukcje `open` na początku pliku `blobs.fsx`:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Uzyskiwanie parametrów połączenia

Potrzebujesz parametrów połączenia usługi Azure Storage dla tego samouczka. Aby uzyskać więcej informacji dotyczących parametrów połączenia, zobacz [Konfigurowanie parametrów połączenia magazynu](/azure/storage/storage-configure-connection-string).

W samouczku wprowadzono parametry połączenia w skrypcie, takie jak:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Nie jest to jednak **zalecane** w przypadku rzeczywistych projektów. Klucz konta magazynu jest podobny do hasła głównego konta magazynu. Zawsze chroń klucz konta magazynu. Nie udostępniaj go innym użytkownikom, nie koduj go trwale ani nie zapisuj w zwykłym pliku tekstowym, do którego mają dostęp inne osoby. Możesz ponownie wygenerować klucz przy użyciu Azure Portal, jeśli uważasz, że jego zabezpieczenia mogły zostać naruszone.

W przypadku prawdziwych aplikacji najlepszym sposobem obsługi parametrów połączenia magazynu jest w pliku konfiguracji. Aby pobrać parametry połączenia z pliku konfiguracji, można to zrobić:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Użycie programu Azure Configuration Manager jest opcjonalne. Można również użyć interfejsu API, takiego jak `ConfigurationManager` typ .NET Framework.

### <a name="parse-the-connection-string"></a>Analizowanie parametrów połączenia

Aby przeanalizować parametry połączenia, użyj:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Spowoduje to zwrócenie elementu `CloudStorageAccount` .

### <a name="create-some-local-dummy-data"></a>Tworzenie niektórych lokalnych danych fikcyjnych

Przed rozpoczęciem Utwórz własne fikcyjne dane lokalne w katalogu naszego skryptu. Później przekażesz te dane.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Tworzenie klienta usługi Blob

`CloudBlobClient`Typ umożliwia pobieranie kontenerów i obiektów BLOB przechowywanych w usłudze BLOB Storage. Oto jeden ze sposobów tworzenia klienta usługi:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

Teraz możesz przystąpić do pisania kodu, który będzie odczytywać dane z Magazynu obiektów blob i zapisywać je w nim.

## <a name="create-a-container"></a>Tworzenie kontenera

W tym przykładzie pokazano, jak utworzyć kontener, jeśli jeszcze nie istnieje:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Domyślnie nowy kontener jest prywatny, co oznacza, że musisz podać klucz dostępu do magazynu, aby pobierać obiekty blob z tego kontenera. Jeśli chcesz, aby pliki w kontenerze były dostępne dla wszystkich, możesz ustawić kontener jako publiczny przy użyciu następującego kodu:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Wszyscy użytkownicy Internetu mogą wyświetlać obiekty blob w kontenerze publicznym, ale można je modyfikować lub usuwać tylko przy użyciu odpowiedniego klucza dostępu do konta lub sygnatury dostępu współdzielonego.

## <a name="upload-a-blob-into-a-container"></a>Przekazywanie obiektu blob do kontenera

Azure Blob Storage obsługuje blokowe i stronicowe obiekty blob. W większości przypadków zalecanym typem jest blokowy obiekt BLOB.

Aby przekazać plik do blokowego obiektu blob, pobierz odwołanie do kontenera i uzyskaj za jego pomocą odwołanie do blokowego obiektu blob. Po uzyskaniu odwołania do obiektu BLOB możesz przekazać do niego dowolny strumień danych, wywołując `UploadFromFile` metodę. Ta operacja tworzy obiekt BLOB, jeśli jeszcze nie istnieje, lub go zastępuje, jeśli istnieje.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Wyświetlanie listy obiektów blob w kontenerze

Aby wyświetlić listę obiektów blob w kontenerze, należy najpierw uzyskać odwołanie do kontenera. Następnie można użyć `ListBlobs` metody kontenera do pobrania obiektów blob i/lub znajdujących się w niej katalogów. Aby uzyskać dostęp do bogatego zestawu właściwości i metod dla zwracanych danych `IListBlobItem` , należy rzutować je `CloudBlockBlob` na `CloudPageBlob` obiekt, lub `CloudBlobDirectory` . Jeśli typ jest nieznany, można zastosować sprawdzanie typu, aby określić, do którego obiektu rzutować obiekt. Poniższy kod przedstawia sposób pobierania i zwracania identyfikatora URI poszczególnych elementów w kontenerze `mydata`:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

Można także nazywać obiekty blob z informacjami o ścieżce w ich nazwach. Powoduje to utworzenie wirtualnej struktury katalogów, które można organizować i przechodzić między nimi tak jak w przypadku tradycyjnego systemu plików. Struktura katalogów jest tylko wirtualna — jedyne zasoby dostępne w usłudze BLOB Storage to kontenery i obiekty blob. Jednak Biblioteka klienta magazynu oferuje `CloudBlobDirectory` obiekt do odwoływania się do katalogu wirtualnego i upraszcza proces pracy z obiektami BLOB zorganizowanymi w ten sposób.

Rozważmy na przykład następujący zestaw blokowych obiektów blob w kontenerze o nazwie `photos`:

*photo1.jpg*\
*2015/architektura/description.txt*\
*2015/architektura/photo3.jpg*\
*2015/architektura/photo4.jpg*\
*2016/architektura/photo5.jpg*\
*2016/architektura/photo6.jpg*\
*2016/architektura/description.txt*\
*2016/photo7.jpg*\

Po wywołaniu `ListBlobs` kontenera (jak w powyższym przykładzie) zwracana jest lista hierarchiczna. Jeśli zawiera zarówno `CloudBlobDirectory` `CloudBlockBlob` obiekt, jak i obiekty, reprezentujące katalogi i obiekty blob w kontenerze, dane wyjściowe wyglądają podobnie do tego:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Opcjonalnie można ustawić `UseFlatBlobListing` parametr `ListBlobs` metody na `true` . W takim przypadku każdy obiekt BLOB w kontenerze jest zwracany jako `CloudBlockBlob` obiekt. Wywołanie `ListBlobs` do zwrócenia płaskiej listy wygląda następująco:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

w zależności od bieżącej zawartości kontenera wyniki wyglądają następująco:

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a>Pobieranie obiektów blob

Aby pobrać obiekty blob, najpierw Pobierz odwołanie do obiektu BLOB, a następnie Wywołaj `DownloadToStream` metodę. W poniższym przykładzie zastosowano `DownloadToStream` metodę transferu zawartości obiektu BLOB do obiektu strumienia, który można następnie przechowywać do pliku lokalnego.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

Możesz również użyć metody, `DownloadToStream` Aby pobrać zawartość obiektu BLOB jako ciąg tekstowy.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Usuwać obiekty blob

Aby usunąć obiekt BLOB, należy najpierw pobrać odwołanie do obiektu BLOB, a następnie wywołać `Delete` metodę.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Asynchroniczne wyświetlanie obiektów blob na stronach

Jeśli chcesz wyświetlić dużą liczbę obiektów blob lub kontrolować liczbę wyników zwracanych przez jedną operację wyświetlania listy, możesz wyświetlić obiekty blob na stronach wyników. W tym przykładzie przedstawiono sposób asynchronicznego zwracania wyników na stronach, dzięki czemu wykonanie nie jest blokowane podczas oczekiwania na zwrócenie dużych zestawów wyników.

Ten przykład pokazuje płaską listę obiektów blob, ale można również wykonać listę hierarchiczną, ustawiając `useFlatBlobListing` parametr `ListBlobsSegmentedAsync` metody na `false` .

Przykład definiuje metodę asynchroniczną przy użyciu `async` bloku. ``let!``Słowo kluczowe zawiesza wykonywanie przykładowej metody do momentu zakończenia zadania tworzenia listy.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

Teraz można użyć tej procedury asynchronicznej w następujący sposób. Najpierw przekażesz niektóre fikcyjne dane (przy użyciu pliku lokalnego utworzonego wcześniej w tym samouczku).

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

Teraz Wywołaj procedurę. Używasz, `Async.RunSynchronously` Aby wymusić wykonanie operacji asynchronicznej.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Zapisywanie do uzupełnialnego obiektu blob

Uzupełnialny obiekt blob jest zoptymalizowany pod kątem operacji dołączania, takich jak rejestrowanie. Podobnie jak blokowy obiekt BLOB, obiekt BLOB dołączania składa się z bloków, ale po dodaniu nowego bloku do dołączanego obiektu BLOB jest on zawsze dołączany na końcu obiektu BLOB. Nie można zaktualizować lub usunąć istniejącego bloku w uzupełnialnym obiekcie blob. Identyfikatory bloków w uzupełnialnym obiekcie blob nie są widoczne, jak w przypadku blokowego obiektu blob.

Każdy blok w uzupełnialnym obiekcie blob może różnić się rozmiarem, który może wynosić maksymalnie 4 MB, a uzupełnialny obiekt blob może zawierać do 50 000 bloków. Z tego względu maksymalny rozmiar uzupełnialnego obiektu blob nieznacznie przekracza 195 GB (4 MB X 50 000 bloków).

Poniższy przykład tworzy nowy obiekt BLOB dołączania i dołącza do niego pewne dane, symulując prostą operację rejestrowania.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Aby uzyskać więcej informacji o różnicach między tymi trzema typami obiektów blob, zobacz [Understanding Block Blobs, Page Blobs, and Append Blobs](/rest/api/storageservices/Understanding-Block-Blobs--Append-Blobs--and-Page-Blobs) (Omówienie blokowych i stronicowych obiektów blob oraz uzupełnialnych obiektów blob).

## <a name="concurrent-access"></a>Równoczesny dostęp

Aby zapewnić obsługę współbieżnego dostępu do obiektu BLOB z wielu klientów lub wielu wystąpień procesów, można użyć elementów **ETags** lub **leases**.

- **ETag** — umożliwia wykrycie, że obiekt BLOB lub kontener został zmodyfikowany przez inny proces

- **Dzierżawa** — umożliwia uzyskanie dostępu do obiektu BLOB na wyłączność, odnowienie, zapis lub usunięcie w danym okresie czasu

Aby uzyskać więcej informacji, zobacz [Zarządzanie współbieżnością w Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Nazywanie kontenerów

Każdy obiekt blob w usłudze Azure Storage musi znajdować się w kontenerze. Kontener jest częścią nazwy obiektu blob. Na przykład `mydata` to nazwa kontenera w następujących przykładowych identyfikatorach URI obiektów blob:

- `https://storagesample.blob.core.windows.net/mydata/blob1.txt`
- `https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg`

Nazwa kontenera musi być prawidłową nazwą DNS zgodną z następującymi zasadami nazewnictwa:

1. Nazwa kontenera musi zaczynać się literą lub cyfrą i może zawierać tylko litery, cyfry i znak kreski (-).
1. Bezpośrednio przed każdym znakiem kreski (-) i bezpośrednio po nim musi występować litera lub cyfra. W nazwach kontenerów następujące po sobie kreski są niedozwolone.
1. Wszystkie litery w nazwie kontenera muszą być małymi literami.
1. Nazwy kontenerów muszą zawierać od 3 do 63 znaków.

Nazwa kontenera musi być zawsze małymi literami. Jeśli w nazwie kontenera wystąpi wielka litera lub reguły nazewnictwa dotyczące kontenerów zostaną naruszone w inny sposób, może zostać wyświetlony błąd 400 (Nieprawidłowe żądanie).

## <a name="managing-security-for-blobs"></a>Zarządzanie zabezpieczeniami obiektów blob

Domyślnie usługa Azure Storage chroni dane, umożliwiając dostęp wyłącznie właścicielowi konta, który ma klucze dostępu do konta. W przypadku potrzeby udostępnienia danych obiektów blob na koncie magazynu ważne jest, aby zrobić to bez uszczerbku dla bezpieczeństwa kluczy dostępu do konta. Dodatkowo można zaszyfrować dane obiektu blob, aby zapewnić ich bezpieczeństwo podczas przesyłania przez sieć oraz w usłudze Azure Storage.

### <a name="controlling-access-to-blob-data"></a>Kontrolowanie dostępu do danych obiektów blob

Domyślnie dane obiektów blob na koncie magazynu są dostępne tylko dla właściciela konta magazynu. Domyślnie do uwierzytelniania żądań dotyczących Magazynu obiektów blob jest wymagany klucz dostępu do konta. Jednak może być konieczne udostępnienie pewnych danych obiektów BLOB innym użytkownikom.

### <a name="encrypting-blob-data"></a>Szyfrowanie danych obiektów blob

Usługa Azure Storage obsługuje szyfrowanie danych obiektów BLOB zarówno na kliencie, jak i na serwerze.

## <a name="next-steps"></a>Następne kroki

Teraz, kiedy znasz już podstawy usługi Blob Storage, skorzystaj z poniższych linków, aby dowiedzieć się więcej.

### <a name="tools"></a>Narzędzia

- [AzureStorageTypeProvider F #](https://fsprojects.github.io/AzureStorageTypeProvider/)\
Dostawca typów języka F #, który może służyć do eksplorowania obiektów blob, tabel i kolejek zasobów usługi Azure Storage oraz łatwego zastosowania na nich CRUD operacji.

- [FSharp. Azure. Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\
Interfejs API języka F # służący do korzystania z usługi Microsoft Azure Table Storage

- [Eksplorator usługi Microsoft Azure Storage (darmową)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\
Bezpłatna, autonomiczna aplikacja oferowana przez firmę Microsoft, która umożliwia wizualne korzystanie z danych usługi Azure Storage w systemach Windows, OS X i Linux.

### <a name="blob-storage-reference"></a>Informacje o usłudze Blob Storage

- [Interfejsy API usługi Azure Storage dla platformy .NET](/dotnet/api/overview/azure/storage)
- [Dokumentacja interfejsu API REST usługi Azure Storage](/rest/api/storageservices/)

### <a name="related-guides"></a>Pokrewne prowadnice

- [Przykłady Blob Storage platformy Azure dla platformy .NET](/samples/azure-samples/storage-blob-dotnet-getting-started/storage-blob-dotnet-getting-started/)
- [Wprowadzenie do narzędzia AzCopy](/azure/storage/common/storage-use-azcopy-v10)
- [Konfiguracja parametrów połączenia usługi Azure Storage](/azure/storage/common/storage-configure-connection-string)
- [Blog zespołu usługi Azure Storage](/archive/blogs/windowsazurestorage/)
- [Szybki start: tworzenie obiektu blob w magazynie obiektów za pomocą platformy .NET](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
