---
title: 'Instrukcje: Dodawanie lub usuwanie pozycji listy Access Control (tylko .NET Framework)'
ms.date: 01/14/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
ms.openlocfilehash: 53daa88b761f46dab26b1c12c73741e880512d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682695"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a>Instrukcje: Dodawanie lub usuwanie pozycji listy Access Control (tylko .NET Framework)

Aby dodać lub usunąć wpisy listy Access Control (ACL) do lub z pliku lub katalogu, Pobierz <xref:System.Security.AccessControl.FileSecurity> <xref:System.Security.AccessControl.DirectorySecurity> obiekt lub z pliku lub katalogu. Zmodyfikuj obiekt, a następnie Zastosuj go z powrotem do pliku lub katalogu.  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a>Dodawanie lub usuwanie wpisu listy ACL z pliku  
  
1. Wywołaj <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> metodę, aby uzyskać <xref:System.Security.AccessControl.FileSecurity> obiekt zawierający bieżące wpisy listy ACL pliku.  
  
2. Dodaj lub Usuń wpisy listy ACL z <xref:System.Security.AccessControl.FileSecurity> obiektu zwróconego z kroku 1.  
  
3. Aby zastosować zmiany, Przekaż <xref:System.Security.AccessControl.FileSecurity> obiekt do <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType> metody.  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a>Dodawanie lub usuwanie wpisu listy ACL z katalogu  
  
1. Wywołaj <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> metodę, aby uzyskać <xref:System.Security.AccessControl.DirectorySecurity> obiekt zawierający bieżące wpisy listy ACL katalogu.  
  
2. Dodaj lub Usuń wpisy listy ACL z <xref:System.Security.AccessControl.DirectorySecurity> obiektu zwróconego z kroku 1.  
  
3. Aby zastosować zmiany, Przekaż <xref:System.Security.AccessControl.DirectorySecurity> obiekt do <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType> metody.  
  
## <a name="example"></a>Przykład  

 Do uruchomienia tego przykładu należy użyć prawidłowego konta użytkownika lub grupy. W przykładzie zastosowano <xref:System.IO.File> obiekt. Użyj tej samej procedury dla <xref:System.IO.FileInfo> klas, <xref:System.IO.Directory> i <xref:System.IO.DirectoryInfo> .

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
