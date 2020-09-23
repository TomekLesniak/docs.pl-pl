---
title: 'Porady: określanie ciągu skojarzonego z wartością wyliczenia'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 4138759bfbb049b77406fc536219b40d3ed9e2a5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058772"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="ca11b-102">Porady: określanie ciągu skojarzonego z wartością wyliczenia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca11b-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>

<span data-ttu-id="ca11b-103"><xref:System.Enum.GetValues%2A>Metody i <xref:System.Enum.GetNames%2A> umożliwiają określanie ciągów i wartości skojarzonych z elementami członkowskimi wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="ca11b-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="ca11b-104">Aby określić ciąg skojarzony z wyliczeniem</span><span class="sxs-lookup"><span data-stu-id="ca11b-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="ca11b-105">Użyj <xref:System.Enum.GetNames%2A> metody, aby pobrać ciągi skojarzone z elementami członkowskimi wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="ca11b-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="ca11b-106">Ten przykład deklaruje Wyliczenie, `flavorEnum` a następnie używa <xref:System.Enum.GetNames%2A> metody do wyświetlania ciągów skojarzonych z poszczególnymi elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="ca11b-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ca11b-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ca11b-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="ca11b-108">Instrukcje: deklarowanie wyliczenia</span><span class="sxs-lookup"><span data-stu-id="ca11b-108">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="ca11b-109">Porady: odwoływanie się do elementu członkowskiego wyliczenia</span><span class="sxs-lookup"><span data-stu-id="ca11b-109">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="ca11b-110">Wyliczenie i kwantyfikacja nazwy</span><span class="sxs-lookup"><span data-stu-id="ca11b-110">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="ca11b-111">Porady: iterowanie za pomocą wyliczania w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca11b-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="ca11b-112">Kiedy stosować wyliczanie</span><span class="sxs-lookup"><span data-stu-id="ca11b-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="ca11b-113">Enum, instrukcja</span><span class="sxs-lookup"><span data-stu-id="ca11b-113">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
