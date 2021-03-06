---
title: 'Instrukcje: przekazywanie pliku'
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: cee6811d6b6d295c28eb683c5d2f7bcbb5fe94ab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401813"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a>Porady: ładowanie pliku w Visual Basic

<xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>Metoda ta umożliwia przekazanie pliku i zapisanie go w lokalizacji zdalnej. Jeśli `ShowUI` parametr jest ustawiony na `True` , wyświetlane jest okno dialogowe, które pokazuje postęp przekazywania i umożliwia użytkownikom anulowanie operacji.  
  
### <a name="to-upload-a-file"></a>Aby przekazać plik  
  
- Za pomocą `UploadFile` metody Przekaż plik, określając lokalizację pliku źródłowego i lokalizację katalogu docelowego jako ciąg lub identyfikator URI (Uniform Resource Identifier). Ten przykład przekazuje plik `Order.txt` do `http://www.cohowinery.com/uploads.aspx` .  
  
     [!code-vb[VbResourceTasks#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#6)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a>Aby przekazać plik i wyświetlić postęp operacji  
  
- Użyj `UploadFile` metody, aby przekazać plik, określając lokalizację pliku źródłowego i lokalizację katalogu docelowego jako ciąg lub identyfikator URI. Ten przykład przekazuje plik `Order.txt` do `http://www.cohowinery.com/uploads.aspx` bez podawania nazwy użytkownika lub hasła, pokazuje postęp przekazywania i ma interwał limitu czasu wynoszący 500 milisekund.  
  
     [!code-vb[VbResourceTasks#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#7)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a>Aby przekazać plik, należy podać nazwę użytkownika i hasło.  
  
- Użyj `UploadFile` metody, aby przekazać plik, określić lokalizację pliku źródłowego i lokalizację katalogu docelowego jako ciąg lub identyfikator URI oraz określić nazwę użytkownika i hasło. Ten przykład przekazuje plik `Order.txt` do `http://www.cohowinery.com/uploads.aspx` , podając nazwę użytkownika `anonymous` i puste hasło.  
  
     [!code-vb[VbResourceTasks#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a>Niezawodne programowanie  

 Następujące warunki mogą zgłosić wyjątek:  
  
- Lokalna ścieżka pliku jest nieprawidłowa ( <xref:System.ArgumentException> ).  
  
- Uwierzytelnianie nie powiodło się ( <xref:System.Security.SecurityException> ).  
  
- Przekroczono limit czasu połączenia ( <xref:System.TimeoutException> ).  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [Instrukcje: pobieranie pliku](how-to-download-a-file.md)
- [Instrukcje: Analizowanie ścieżek plików](../drives-directories-files/how-to-parse-file-paths.md)
