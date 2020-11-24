---
title: ISymUnmanagedDocument — Interfejs
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: 83c683e1f60f13f7cee4ddc6fe5af5a94e36eb93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692179"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="50531-102">ISymUnmanagedDocument — Interfejs</span><span class="sxs-lookup"><span data-stu-id="50531-102">ISymUnmanagedDocument Interface</span></span>

<span data-ttu-id="50531-103">Reprezentuje dokument, do którego odwołuje się magazyn symboli.</span><span class="sxs-lookup"><span data-stu-id="50531-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="50531-104">Dokument jest zdefiniowany przez adres URL (Uniform Resource Locator) i identyfikator GUID typu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="50531-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="50531-105">Możesz zlokalizować dokument niezależnie od tego, w jaki sposób jest przechowywany przy użyciu adresu URL i identyfikatora GUID typu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="50531-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="50531-106">Źródło dokumentu można zapisać w magazynie symboli i pobrać je za pomocą tego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="50531-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50531-107">Metody</span><span class="sxs-lookup"><span data-stu-id="50531-107">Methods</span></span>  
  
|<span data-ttu-id="50531-108">Metoda</span><span class="sxs-lookup"><span data-stu-id="50531-108">Method</span></span>|<span data-ttu-id="50531-109">Opis</span><span class="sxs-lookup"><span data-stu-id="50531-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50531-110">FindClosestLine, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="50531-111">Zwraca najbliższy wiersz będący punktem sekwencji, uwzględniając wiersz w tym dokumencie, który może lub nie jest punktem sekwencji.</span><span class="sxs-lookup"><span data-stu-id="50531-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="50531-112">GetCheckSum, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="50531-113">Pobiera sumę kontrolną.</span><span class="sxs-lookup"><span data-stu-id="50531-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="50531-114">GetCheckSumAlgorithmId, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="50531-115">Pobiera identyfikator algorytmu sum kontrolnych lub zwraca identyfikator GUID wszystkich zer, jeśli nie ma sumy kontrolnej.</span><span class="sxs-lookup"><span data-stu-id="50531-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="50531-116">GetDocumentType, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="50531-117">Pobiera typ dokumentu tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="50531-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="50531-118">GetLanguage, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="50531-119">Pobiera identyfikator języka tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="50531-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="50531-120">GetLanguageVendor, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="50531-121">Pobiera dostawcę języka tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="50531-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="50531-122">GetSourceLength, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="50531-123">Pobiera długość (w bajtach) osadzonego źródła.</span><span class="sxs-lookup"><span data-stu-id="50531-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="50531-124">GetSourceRange, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="50531-125">Zwraca określony zakres osadzonego źródła do podanego buforu.</span><span class="sxs-lookup"><span data-stu-id="50531-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="50531-126">GetURL, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="50531-127">Zwraca adres URL tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="50531-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="50531-128">HasEmbeddedSource, metoda</span><span class="sxs-lookup"><span data-stu-id="50531-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="50531-129">Zwraca `true` czy dokument ma osadzone źródło w symbolach debugowania; w przeciwnym razie zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="50531-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50531-130">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="50531-130">See also</span></span>

- [<span data-ttu-id="50531-131">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="50531-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
