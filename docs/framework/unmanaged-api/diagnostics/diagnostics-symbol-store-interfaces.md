---
title: Interfejsy magazynu symboli diagnostycznych
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: e376544a9d428ce5110a7e38b92a8e830f574664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725186"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="f6424-102">Interfejsy magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="f6424-102">Diagnostics Symbol Store Interfaces</span></span>

<span data-ttu-id="f6424-103">W tym temacie opisano niezarządzane interfejsy, które umożliwiają kompilatorowi generowanie informacji o symbolach do użycia przez debuger.</span><span class="sxs-lookup"><span data-stu-id="f6424-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6424-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="f6424-104">In This Section</span></span>  

 [<span data-ttu-id="f6424-105">IBindingDisplay — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-105">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="f6424-106">Dostarcza metody, które wyświetlają bieżące informacje o powiązaniu dla działającej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f6424-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="f6424-107">IDebugAutoAttach — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-107">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="f6424-108">Definiuje interfejs dla automatycznie dołączanego debugera dla serwera.</span><span class="sxs-lookup"><span data-stu-id="f6424-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="f6424-109">INotifyConnection2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-109">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="f6424-110">Deklaruje metody rejestrowania źródła powiadomień połączenia i wyrejestrowywania go.</span><span class="sxs-lookup"><span data-stu-id="f6424-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="f6424-111">INotifySink2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-111">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="f6424-112">Deklaruje metody powiadamiania o ujściach.</span><span class="sxs-lookup"><span data-stu-id="f6424-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="f6424-113">INotifySource2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="f6424-114">Deklaruje metodę ustawiania filtrów powiadomień.</span><span class="sxs-lookup"><span data-stu-id="f6424-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="f6424-115">ISymENCUnmanagedMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="f6424-116">Zawiera informacje dotyczące funkcji Edytuj i Kontynuuj.</span><span class="sxs-lookup"><span data-stu-id="f6424-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="f6424-117">ISymUnmanagedAsyncMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-117">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="f6424-118">Ten interfejs jest uzupełnieniem odczytu do [interfejsu ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f6424-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="f6424-119">ISymUnmanagedAsyncMethodPropertiesWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="f6424-120">Zezwala na definiowanie opcjonalnych informacji o metodzie asynchronicznej dla symbolu metody.</span><span class="sxs-lookup"><span data-stu-id="f6424-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="f6424-121">Musi być używana z otwartą metodą (czyli między wywołaniami [metody OpenMethod —](isymunmanagedwriter-openmethod-method.md)i [CloseMethod —](isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="f6424-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="f6424-122">ISymUnmanagedBinder — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-122">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="f6424-123">Reprezentuje spinacz symboliczny dla niezarządzanego kodu.</span><span class="sxs-lookup"><span data-stu-id="f6424-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="f6424-124">ISymUnmanagedBinder2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-124">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="f6424-125">Reprezentuje segregator symboliczny dla kodu niezarządzanego i rozszerza `ISymUnmanagedBinder` interfejs.</span><span class="sxs-lookup"><span data-stu-id="f6424-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="f6424-126">ISymUnmanagedBinder3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-126">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="f6424-127">Reprezentuje segregator symboliczny dla kodu niezarządzanego i rozszerza `ISymUnmanagedBinder` interfejs.</span><span class="sxs-lookup"><span data-stu-id="f6424-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="f6424-128">ISymUnmanagedConstant — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-128">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="f6424-129">Zapewnia dostęp do stałych niezarządzanych.</span><span class="sxs-lookup"><span data-stu-id="f6424-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="f6424-130">ISymUnmanagedDispose — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-130">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="f6424-131">Usuwa niezarządzane zasoby.</span><span class="sxs-lookup"><span data-stu-id="f6424-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="f6424-132">ISymUnmanagedDocument — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-132">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="f6424-133">Reprezentuje dokument, do którego odwołuje się magazyn symboli.</span><span class="sxs-lookup"><span data-stu-id="f6424-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="f6424-134">ISymUnmanagedDocumentWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-134">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="f6424-135">Zapewnia metody zapisu do dokumentu, do którego odwołuje się magazyn symboli.</span><span class="sxs-lookup"><span data-stu-id="f6424-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="f6424-136">ISymUnmanagedENCUpdate — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-136">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="f6424-137">Zapewnia metody funkcji Edytuj i Kontynuuj.</span><span class="sxs-lookup"><span data-stu-id="f6424-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="f6424-138">ISymUnmanagedMethod — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-138">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="f6424-139">Reprezentuje metodę w magazynie symboli.</span><span class="sxs-lookup"><span data-stu-id="f6424-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="f6424-140">ISymUnmanagedNamespace — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-140">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="f6424-141">Reprezentuje przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="f6424-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="f6424-142">ISymUnmanagedReader — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-142">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="f6424-143">Reprezentuje czytnik symboli, który zapewnia dostęp do dokumentów, metod i zmiennych w magazynie symboli.</span><span class="sxs-lookup"><span data-stu-id="f6424-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="f6424-144">ISymUnmanagedReader2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-144">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="f6424-145">Pobiera metodę czytnika symboli, używając tokenu metody oraz numeru wersji Edit-and-Copy.</span><span class="sxs-lookup"><span data-stu-id="f6424-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="f6424-146">ISymUnmanagedReaderSymbolSearchInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="f6424-147">Dostarcza metody, które pobierają informacje o wyszukiwaniu symboli.</span><span class="sxs-lookup"><span data-stu-id="f6424-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="f6424-148">ISymUnmanagedScope — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-148">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="f6424-149">Reprezentuje zakres leksykalny w ramach metody.</span><span class="sxs-lookup"><span data-stu-id="f6424-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="f6424-150">ISymUnmanagedScope2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-150">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="f6424-151">Reprezentuje zakres leksykalny w ramach metody i rozszerza `ISymUnmanagedScope` interfejs przy użyciu metod, które pobierają informacje o stałych zdefiniowanych w zakresie.</span><span class="sxs-lookup"><span data-stu-id="f6424-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="f6424-152">ISymUnmanagedSourceServerModule — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-152">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="f6424-153">Zapewnia dane serwera źródłowego dla modułu.</span><span class="sxs-lookup"><span data-stu-id="f6424-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="f6424-154">ISymUnmanagedSymbolSearchInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="f6424-155">Dostarcza metody, które pobierają informacje o ścieżce wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="f6424-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="f6424-156">ISymUnmanagedVariable — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-156">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="f6424-157">Reprezentuje zmienną, taką jak parametr, zmienna lokalna lub pole.</span><span class="sxs-lookup"><span data-stu-id="f6424-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="f6424-158">ISymUnmanagedWriter — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-158">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="f6424-159">Reprezentuje moduł zapisujący symboli i zawiera metody definiowania dokumentów, punktów sekwencji, zakresów leksykalnych i zmiennych.</span><span class="sxs-lookup"><span data-stu-id="f6424-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="f6424-160">ISymUnmanagedWriter2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="f6424-161">Reprezentuje moduł zapisujący symboli i zawiera metody definiowania dokumentów, punktów sekwencji, zakresów leksykalnych i zmiennych.</span><span class="sxs-lookup"><span data-stu-id="f6424-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="f6424-162">Rozszerza `ISymUnmanagedWriter` interfejs.</span><span class="sxs-lookup"><span data-stu-id="f6424-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="f6424-163">ISymUnmanagedWriter3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-163">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="f6424-164">Reprezentuje moduł zapisujący symboli i zawiera metody definiowania dokumentów, punktów sekwencji, zakresów leksykalnych i zmiennych.</span><span class="sxs-lookup"><span data-stu-id="f6424-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="f6424-165">Rozszerza `ISymUnmanagedWriter` interfejs.</span><span class="sxs-lookup"><span data-stu-id="f6424-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="f6424-166">ISymUnmanagedWriter4 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-166">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="f6424-167">Interfejs ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="f6424-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="f6424-168">ISymUnmanagedWriter5 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f6424-168">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="f6424-169">Interfejs ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="f6424-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f6424-170">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="f6424-170">Related Sections</span></span>  

 [<span data-ttu-id="f6424-171">Wyliczenia magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="f6424-171">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="f6424-172">Struktury magazynu symboli diagnostycznych</span><span class="sxs-lookup"><span data-stu-id="f6424-172">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="f6424-173">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="f6424-173">Debugging</span></span>](../debugging/index.md)
