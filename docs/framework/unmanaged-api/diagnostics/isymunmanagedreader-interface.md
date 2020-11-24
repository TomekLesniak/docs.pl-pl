---
title: ISymUnmanagedReader — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: bca84fdba575ed9bfe572b9fd7a5869620962de6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675870"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="5db41-102">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5db41-102">ISymUnmanagedReader Interface</span></span>

<span data-ttu-id="5db41-103">Reprezentuje czytnik symboli, który zapewnia dostęp do dokumentów, metod i zmiennych w magazynie symboli.</span><span class="sxs-lookup"><span data-stu-id="5db41-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5db41-104">Metody</span><span class="sxs-lookup"><span data-stu-id="5db41-104">Methods</span></span>  
  
|<span data-ttu-id="5db41-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-105">Method</span></span>|<span data-ttu-id="5db41-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5db41-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5db41-107">GetDocument, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-107">GetDocument Method</span></span>](isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="5db41-108">Znajduje dokument.</span><span class="sxs-lookup"><span data-stu-id="5db41-108">Finds a document.</span></span>|  
|[<span data-ttu-id="5db41-109">GetDocuments, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-109">GetDocuments Method</span></span>](isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="5db41-110">Zwraca tablicę wszystkich dokumentów zdefiniowanych w magazynie symboli.</span><span class="sxs-lookup"><span data-stu-id="5db41-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="5db41-111">GetDocumentVersion, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-111">GetDocumentVersion Method</span></span>](isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="5db41-112">Pobiera określoną wersję określonego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="5db41-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="5db41-113">GetGlobalVariables, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-113">GetGlobalVariables Method</span></span>](isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="5db41-114">Zwraca wszystkie zmienne globalne.</span><span class="sxs-lookup"><span data-stu-id="5db41-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="5db41-115">GetMethod, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-115">GetMethod Method</span></span>](isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="5db41-116">Pobiera metodę czytnika symboli, używając tokenu metody.</span><span class="sxs-lookup"><span data-stu-id="5db41-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="5db41-117">GetMethodByVersion, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-117">GetMethodByVersion Method</span></span>](isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="5db41-118">Pobiera metodę czytnika symboli, uwzględniając token metody i numer wersji do edycji i kopiowania.</span><span class="sxs-lookup"><span data-stu-id="5db41-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="5db41-119">GetMethodFromDocumentPosition, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-119">GetMethodFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="5db41-120">Zwraca metodę, która zawiera punkt przerwania w podanym miejscu w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="5db41-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="5db41-121">GetMethodsFromDocumentPosition, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-121">GetMethodsFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="5db41-122">Zwraca tablicę metod, z których każdy zawiera punkt przerwania w podanym miejscu w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="5db41-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="5db41-123">GetMethodVersion, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-123">GetMethodVersion Method</span></span>](isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="5db41-124">Pobiera wersję metody.</span><span class="sxs-lookup"><span data-stu-id="5db41-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="5db41-125">GetNamespaces, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-125">GetNamespaces Method</span></span>](isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="5db41-126">Pobiera przestrzenie nazw zdefiniowane w globalnym zakresie w ramach tego magazynu symboli.</span><span class="sxs-lookup"><span data-stu-id="5db41-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="5db41-127">GetSymAttribute, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-127">GetSymAttribute Method</span></span>](isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="5db41-128">Pobiera atrybut niestandardowy na podstawie jego nazwy.</span><span class="sxs-lookup"><span data-stu-id="5db41-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="5db41-129">GetSymbolStoreFileName, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-129">GetSymbolStoreFileName Method</span></span>](isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="5db41-130">Udostępnia nazwę pliku na dysku magazynu symboli.</span><span class="sxs-lookup"><span data-stu-id="5db41-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="5db41-131">GetUserEntryPoint, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-131">GetUserEntryPoint Method</span></span>](isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="5db41-132">Zwraca metodę, która została określona jako punkt wejścia użytkownika dla modułu, jeśli istnieje.</span><span class="sxs-lookup"><span data-stu-id="5db41-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="5db41-133">GetVariables, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-133">GetVariables Method</span></span>](isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="5db41-134">Zwróć zmienną nielokalną, używając jej elementu nadrzędnego i nazwy.</span><span class="sxs-lookup"><span data-stu-id="5db41-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="5db41-135">Initialize — Metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-135">Initialize Method</span></span>](isymunmanagedreader-initialize-method.md)|<span data-ttu-id="5db41-136">Inicjuje czytnik symboli z interfejsem importera metadanych, z którym zostanie skojarzony ten czytnik, wraz z nazwą pliku modułu.</span><span class="sxs-lookup"><span data-stu-id="5db41-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="5db41-137">ReplaceSymbolStore, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-137">ReplaceSymbolStore Method</span></span>](isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="5db41-138">Zamienia istniejący magazyn symboli na magazyn symboli różnicowych.</span><span class="sxs-lookup"><span data-stu-id="5db41-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="5db41-139">UpdateSymbolStore, metoda</span><span class="sxs-lookup"><span data-stu-id="5db41-139">UpdateSymbolStore Method</span></span>](isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="5db41-140">Aktualizuje istniejący magazyn symboli przy użyciu magazynu symboli różnicowych.</span><span class="sxs-lookup"><span data-stu-id="5db41-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5db41-141">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5db41-141">Requirements</span></span>  

 <span data-ttu-id="5db41-142">**Nagłówek:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5db41-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db41-143">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5db41-143">See also</span></span>

- [<span data-ttu-id="5db41-144">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="5db41-144">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="5db41-145">ISymUnmanagedReader2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5db41-145">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
