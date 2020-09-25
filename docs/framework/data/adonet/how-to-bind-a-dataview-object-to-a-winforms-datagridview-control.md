---
title: 'Instrukcje: Wiązanie obiektu widoku danych z kontrolką DataGridView formularzy systemu Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: cf2a47c5d29c0af680ee4ccae503e92d3a9124d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194716"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>Instrukcje: Wiązanie obiektu widoku danych z kontrolką DataGridView formularzy systemu Windows

<xref:System.Windows.Forms.DataGridView>Formant zapewnia zaawansowany i elastyczny sposób wyświetlania danych w formacie tabelarycznym. <xref:System.Windows.Forms.DataGridView>Formant obsługuje model powiązań danych w warstwie standardowa Windows Forms, więc zostanie powiązany z <xref:System.Data.DataView> wieloma innymi źródłami danych i z nich. W większości sytuacji należy jednak powiązać ze <xref:System.Windows.Forms.BindingSource> składnikiem, który będzie zarządzać szczegółami współpracy ze źródłem danych.  
  
 Aby uzyskać więcej informacji na temat <xref:System.Windows.Forms.DataGridView> kontrolki, zobacz [formant DataGridView — Omówienie](/dotnet/desktop/winforms/controls/datagridview-control-overview-windows-forms).  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>Aby połączyć formant DataGridView z obiektem DataView  
  
1. Zaimplementuj metodę, aby obsłużyć Szczegóły pobierania danych z bazy danych. Poniższy przykład kodu implementuje `GetData` metodę inicjującą <xref:System.Data.SqlClient.SqlDataAdapter> składnik i używa jej do wypełnienia <xref:System.Data.DataSet> . Pamiętaj, aby ustawić `connectionString` zmienną na wartość odpowiednią dla bazy danych. Będziesz potrzebować dostępu do serwera z zainstalowaną przykładową bazą danych SQL Server AdventureWorks.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. W <xref:System.Windows.Forms.Form.Load> procedurze obsługi zdarzeń formularza Powiąż <xref:System.Windows.Forms.DataGridView> formant ze <xref:System.Windows.Forms.BindingSource> składnikiem i Wywołaj `GetData` metodę, aby pobrać dane z bazy danych. Program <xref:System.Data.DataView> jest tworzony na podstawie zapytania LINQ to DataSet w ramach kontaktu <xref:System.Data.DataTable> , a następnie jest powiązany ze <xref:System.Windows.Forms.BindingSource> składnikiem.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>Zobacz też

- [Powiązanie danych i LINQ to DataSet](data-binding-and-linq-to-dataset.md)
