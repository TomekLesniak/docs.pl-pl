---
title: Nawigowanie po elementach automatyzacji interfejsu użytkownika przy użyciu opcji TreeWalker
description: Zobacz przykład kodu, który pokazuje, jak nawigować między elementami automatyzacji interfejsu użytkownika za pomocą klasy użyciu opcji TreeWalker.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: e102e6ce258bef06d1fb44decfa1a3a27384e0bc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261218"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>Nawigowanie po elementach automatyzacji interfejsu użytkownika przy użyciu opcji TreeWalker

> [!NOTE]
> Ta dokumentacja jest przeznaczona dla .NET Framework deweloperów, którzy chcą korzystać z zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw. Aby uzyskać najnowsze informacje na temat [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , zobacz [interfejs API usługi Windows Automation: Automatyzacja interfejsu użytkownika](/windows/win32/winauto/entry-uiauto-win32).  
  
 Ten temat zawiera przykładowy kod, który pokazuje, jak przechodzić między [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementami przy użyciu <xref:System.Windows.Automation.TreeWalker> klasy.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa do przeszukiwania <xref:System.Windows.Automation.TreeWalker.GetParent%2A> [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] drzewa do momentu znalezienia elementu głównego lub pulpitu. Element poniżej, który jest oknem nadrzędnym określonego elementu.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład używa <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> i <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> do tworzenia <xref:System.Windows.Forms.TreeView> , który pokazuje Całe poddrzewo elementów znajdujących [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] się w widoku kontrolki, które są włączone.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>Zobacz też

- [Uzyskiwanie elementów automatyzacji interfejsu użytkownika](obtaining-ui-automation-elements.md)
