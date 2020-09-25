---
title: 'Instrukcje: Określanie, które elementy członkowskie są sprawdzane pod kątem konfliktów współbieżności'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: e774935827934ae73873247def049b4045535272
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197147"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a>Instrukcje: Określanie, które elementy członkowskie są sprawdzane pod kątem konfliktów współbieżności

Zastosuj jeden z trzech typów wyliczeniowych do [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> właściwości <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu, aby określić, które składowe mają być uwzględnione w testach aktualizacji w celu wykrywania optymistycznych konfliktów współbieżności.  
  
 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>Właściwość (zamapowana w czasie projektowania) jest używana razem z funkcjami współbieżności w czasie wykonywania w systemie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] . Aby uzyskać więcej informacji, zobacz [optymistyczne współbieżność: Omówienie](optimistic-concurrency-overview.md).  
  
> [!NOTE]
> Pierwotne wartości elementów członkowskich są porównywane z bieżącym stanem bazy danych, o ile nie wyznaczono żadnego elementu członkowskiego `IsVersion=true` . Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
 Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> .  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a>Aby zawsze używać tego elementu członkowskiego do wykrywania konfliktów  
  
1. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
2. Ustaw <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> wartość właściwości na `Always` .  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a>Aby nigdy nie używać tego elementu członkowskiego do wykrywania konfliktów  
  
1. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
2. Ustaw <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> wartość właściwości na `Never` .  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a>Aby użyć tego elementu członkowskiego do wykrywania konfliktów tylko wtedy, gdy aplikacja zmieniła wartość elementu członkowskiego  
  
1. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
2. Ustaw <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> wartość właściwości na `WhenChanged` .  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie określono, że `HomePage` obiekty nigdy nie powinny być testowane podczas sprawdzania aktualizacji. Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: Zarządzanie konfliktami zmian](how-to-manage-change-conflicts.md)
- [Tworzenie i przesyłanie zmian danych](making-and-submitting-data-changes.md)
