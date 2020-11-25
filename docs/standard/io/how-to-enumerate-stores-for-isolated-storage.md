---
title: 'Instrukcje: Wykazywanie magazynów dla izolowanego magazynu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
ms.openlocfilehash: f01ca70b3fd5b778274ef5bd7fcb63e26d9916a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734650"
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a><span data-ttu-id="73248-102">Instrukcje: Wykazywanie magazynów dla izolowanego magazynu</span><span class="sxs-lookup"><span data-stu-id="73248-102">How to: Enumerate Stores for Isolated Storage</span></span>

<span data-ttu-id="73248-103">Wszystkie magazyny izolowane dla bieżącego użytkownika można wyliczyć przy użyciu  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> metody statycznej.</span><span class="sxs-lookup"><span data-stu-id="73248-103">You can enumerate all isolated stores for the current user by using the  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> static method.</span></span> <span data-ttu-id="73248-104">Ta metoda przyjmuje <xref:System.IO.IsolatedStorage.IsolatedStorageScope> wartość i zwraca <xref:System.IO.IsolatedStorage.IsolatedStorageFile> moduł wyliczający.</span><span class="sxs-lookup"><span data-stu-id="73248-104">This  method takes an <xref:System.IO.IsolatedStorage.IsolatedStorageScope> value and returns an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> enumerator.</span></span> <span data-ttu-id="73248-105">Aby wyliczyć magazyny, musisz mieć <xref:System.Security.Permissions.IsolatedStorageFilePermission> uprawnienie określające <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> wartość.</span><span class="sxs-lookup"><span data-stu-id="73248-105">To enumerate stores, you must have the <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission that specifies the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span> <span data-ttu-id="73248-106">W przypadku wywołania <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> metody z <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> wartością zwraca tablicę <xref:System.IO.IsolatedStorage.IsolatedStorageFile> obiektów, które są zdefiniowane dla bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="73248-106">If you call the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method with the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> value, it returns an array of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that are defined for the current user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73248-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="73248-107">Example</span></span>  

 <span data-ttu-id="73248-108">Poniższy przykład kodu pobiera magazyn izolowany przez użytkownika i zestaw, tworzy kilka plików i pobiera te pliki przy użyciu <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="73248-108">The following code example obtains a store that is isolated by user and assembly, creates a few files, and retrieves those files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="73248-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="73248-109">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="73248-110">Magazyn izolowany</span><span class="sxs-lookup"><span data-stu-id="73248-110">Isolated Storage</span></span>](isolated-storage.md)
