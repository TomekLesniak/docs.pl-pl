---
title: 'Instrukcje: ręczne generowanie klas usługi danych klienta (Usługi danych programu WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 368f2546652d21be44c0ffb4cc5f279c56beda51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165995"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>Instrukcje: ręczne generowanie klas usługi danych klienta (Usługi danych programu WCF)

Usługi danych programu WCF integruje się z programem Visual Studio, aby umożliwić automatyczne generowanie klas usługi danych klienta w przypadku używania okna dialogowego **Dodaj odwołanie do usługi** do dodawania odwołania do usługi danych w projekcie programu Visual Studio. Aby uzyskać więcej informacji, zobacz [jak: Dodawanie odwołania do usługi danych](how-to-add-a-data-service-reference-wcf-data-services.md). Można również ręcznie generować te same klasy usługi danych klienta przy użyciu narzędzia do generowania kodu `DataSvcUtil.exe` . To narzędzie, które jest dołączone do Usługi danych programu WCF, generuje klasy .NET Framework z definicji usługi danych. Można go również użyć do wygenerowania klas usługi danych z pliku modelu koncepcyjnego (. csdl) i pliku edmx, który reprezentuje model Entity Framework w projekcie programu Visual Studio.

 W przykładzie w tym temacie opisano tworzenie klas usługi danych klienta na podstawie przykładowej usługi danych Northwind. Ta usługa jest tworzona po zakończeniu [usługi danych programu WCF przewodnika Szybki Start](quickstart-wcf-data-services.md). Niektóre przykłady w tym temacie wymagają pliku modelu koncepcyjnego dla modelu Northwind. Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by wygenerować model i pliki mapowania](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md). Niektóre przykłady w tym temacie wymagają pliku. edmx dla modelu Northwind. Aby uzyskać więcej informacji, zobacz [plik. edmx — Omówienie](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).

### <a name="to-generate-c-classes-that-support-data-binding"></a>Aby wygenerować klasy języka C# obsługujące powiązanie danych

- W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Należy zastąpić wartość dostarczoną do `/uri:` parametru identyfikatorem URI wystąpienia przykładowej usługi danych Northwind.

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>Aby wygenerować klasy Visual Basic obsługujące powiązanie danych

- W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Należy zastąpić wartość dostarczoną do `/uri:` parametru identyfikatorem URI wystąpienia przykładowej usługi danych Northwind.

### <a name="to-generate-c-classes-based-on-the-service-uri"></a>Aby wygenerować klasy C# na podstawie identyfikatora URI usługi

- W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Należy zastąpić wartość dostarczoną do `/uri:` parametru identyfikatorem URI wystąpienia przykładowej usługi danych Northwind.

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>Aby wygenerować klasy Visual Basic na podstawie identyfikatora URI usługi

- W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Należy zastąpić wartość dostarczoną do `/uri:` parametru identyfikatorem URI wystąpienia przykładowej usługi danych Northwind.

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>Aby wygenerować klasy C# na podstawie pliku modelu koncepcyjnego (CSDL)

- W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>Aby wygenerować klasy Visual Basic na podstawie pliku modelu koncepcyjnego (CSDL)

- W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>Aby wygenerować klasy C# na podstawie pliku. edmx

- W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>Aby wygenerować klasy Visual Basic na podstawie pliku. edmx

- W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a>Zobacz też

- [Generowanie biblioteki klienta usługi danych](generating-the-data-service-client-library-wcf-data-services.md)
- [Instrukcje: Dodawanie odwołania do usługi danych](how-to-add-a-data-service-reference-wcf-data-services.md)
- [Narzędzie klienta usługi danych WCF (DataSvcUtil.exe)](wcf-data-service-client-utility-datasvcutil-exe.md)
