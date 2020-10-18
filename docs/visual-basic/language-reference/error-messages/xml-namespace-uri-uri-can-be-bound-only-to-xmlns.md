---
title: Identyfikator URI „<uri>” przestrzeni nazw XML może być powiązany tylko z elementem „xmlns”
ms.date: 07/20/2015
f1_keywords:
- bc31183
- vbc31183
helpviewer_keywords:
- BC31183
ms.assetid: 0ab1dbce-8397-4959-b2cd-f58798b051a0
ms.openlocfilehash: 1aec6ac0a354bfe7e0378a2e46a70a7161bf6d36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163249"
---
# <a name="bc31183-xml-namespace-uri-httpwwww3orgxml1998namespace-can-be-bound-only-to-xmlns"></a><span data-ttu-id="9a09c-102">BC31183: identyfikator URI przestrzeni nazw XML `http://www.w3.org/XML/1998/namespace` ; może być powiązany tylko z elementem "xmlns"</span><span class="sxs-lookup"><span data-stu-id="9a09c-102">BC31183: XML namespace URI `http://www.w3.org/XML/1998/namespace`; can be bound only to 'xmlns'</span></span>

<span data-ttu-id="9a09c-103">Identyfikator URI `http://www.w3.org/XML/1998/namespace` jest używany w deklaracji przestrzeni nazw XML.</span><span class="sxs-lookup"><span data-stu-id="9a09c-103">The URI `http://www.w3.org/XML/1998/namespace` is used in an XML namespace declaration.</span></span> <span data-ttu-id="9a09c-104">Ten identyfikator URI jest zarezerwowaną przestrzenią nazw i nie można go uwzględnić w deklaracji przestrzeni nazw XML.</span><span class="sxs-lookup"><span data-stu-id="9a09c-104">This URI is a reserved namespace and cannot be included in an XML namespace declaration.</span></span>

 <span data-ttu-id="9a09c-105">**Identyfikator błędu:** BC31183</span><span class="sxs-lookup"><span data-stu-id="9a09c-105">**Error ID:** BC31183</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9a09c-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="9a09c-106">To correct this error</span></span>

<span data-ttu-id="9a09c-107">Usuń deklarację przestrzeni nazw XML lub Zastąp identyfikator URI `http://www.w3.org/XML/1998/namespace` prawidłowym identyfikatorem URI przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9a09c-107">Remove the XML namespace declaration or replace the URI `http://www.w3.org/XML/1998/namespace` with a valid namespace URI.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a09c-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a09c-108">See also</span></span>

- [<span data-ttu-id="9a09c-109">Imports — Instrukcja (przestrzeń nazw XML)</span><span class="sxs-lookup"><span data-stu-id="9a09c-109">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="9a09c-110">Literały XML</span><span class="sxs-lookup"><span data-stu-id="9a09c-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="9a09c-111">XML</span><span class="sxs-lookup"><span data-stu-id="9a09c-111">XML</span></span>](../../programming-guide/language-features/xml/index.md)
