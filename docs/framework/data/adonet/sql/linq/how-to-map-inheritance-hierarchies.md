---
title: 'Instrukcje: Mapowanie hierarchii dziedziczenia'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: c0709fde96a5d2f39f04a08ccd24ddf90c782f30
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166420"
---
# <a name="how-to-map-inheritance-hierarchies"></a>Instrukcje: Mapowanie hierarchii dziedziczenia

Aby zaimplementować mapowanie dziedziczenia w LINQ, należy określić atrybuty i właściwości atrybutów w klasie głównej hierarchii dziedziczenia, zgodnie z opisem w poniższych krokach. Deweloperzy korzystający z programu Visual Studio mogą mapować hierarchie dziedziczenia przy użyciu Object Relational Designer. Zobacz [jak: Konfigurowanie dziedziczenia przy użyciu narzędzia O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).  
  
> [!NOTE]
> Dla podklas nie są wymagane żadne specjalne atrybuty ani właściwości. Należy zwrócić uwagę na to, że podklasy nie mają <xref:System.Data.Linq.Mapping.TableAttribute> atrybutu.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>Aby zmapować hierarchię dziedziczenia  
  
1. Dodaj <xref:System.Data.Linq.Mapping.TableAttribute> atrybut do klasy głównej.  
  
2. Także do klasy głównej, Dodaj <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> atrybut dla każdej klasy w strukturze hierarchii.  
  
3. Dla każdego <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> atrybutu Zdefiniuj <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> Właściwość.  
  
     Ta właściwość zawiera wartość, która pojawia się w tabeli bazy danych w <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> kolumnie, aby wskazać klasę lub podklasę, do której należy ten wiersz danych.  
  
4. Dla każdego <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> atrybutu, należy również dodać <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> Właściwość.  
  
     Ta właściwość zawiera wartość określającą klasę lub podklasę wartość klucza.  
  
5. Tylko jeden z <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> atrybutów, Dodaj <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> Właściwość.  
  
     Ta właściwość służy do wyznaczania mapowania *rezerwowego* , gdy wartość rozróżniacza z tabeli bazy danych nie jest zgodna z żadną <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> wartością w mapowaniu dziedziczenia.  
  
6. Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> Właściwość dla <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.  
  
     Ta właściwość oznacza, że jest to kolumna, która zawiera <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> wartość.  
  
## <a name="example"></a>Przykład  
  
> [!NOTE]
> Jeśli używasz programu Visual Studio, możesz użyć Object Relational Designer, aby skonfigurować dziedziczenie. Zobacz [jak: Konfigurowanie dziedziczenia przy użyciu projektanta o/R](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)  
  
 W poniższym przykładzie kodu `Vehicle` jest zdefiniowany jako Klasa główna, a poprzednie kroki zostały zaimplementowane w celu opisania hierarchii dla LINQ.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Zobacz też

- [Obsługa dziedziczenia](inheritance-support.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](how-to-customize-entity-classes-by-using-the-code-editor.md)
