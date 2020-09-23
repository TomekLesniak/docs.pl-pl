---
title: Obsługa funkcji msxsl:node-set()
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
ms.openlocfilehash: 30652d8cbaac333cc1cb35954742b16dc7c4764b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071992"
---
# <a name="support-for-the-msxslnode-set-function"></a>Obsługa funkcji msxsl:node-set()
`msxsl:node-set`Funkcja umożliwia konwertowanie fragmentu drzewa wynikowego na zestaw węzłów. Zestaw węzłów powstających zawsze zawiera pojedynczy węzeł i jest węzłem głównym drzewa.  
  
> [!NOTE]
> <xref:System.Xml.Xsl.XslTransform>Klasa jest przestarzała w .NET Framework 2,0. Można wykonać przekształcenia Extensible Stylesheet Language for Transformations (XSLT) przy użyciu <xref:System.Xml.Xsl.XslCompiledTransform> klasy. Aby uzyskać więcej informacji, zobacz [Używanie klasy XslCompiledTransform](using-the-xslcompiledtransform-class.md) i [Migrowanie z klasy XslTransform](migrating-from-the-xsltransform-class.md) .  
  
 `msxsl:node-set`Funkcja umożliwia konwertowanie fragmentu drzewa wynikowego na zestaw węzłów. Zestaw węzłów powstających zawsze zawiera pojedynczy węzeł i jest węzłem głównym drzewa.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie `$books` jest to zmienna, która jest drzewem węzła w arkuszu stylów. Instrukcja for-each łączona z `node-set` funkcją pozwala użytkownikowi na iterację tego drzewa węzłów jako zestawu węzłów.  
  
## <a name="nodesetxsl"></a>NodeSet. xsl  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">
                <author><xsl:value-of select="@author"/></author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a>Dane wyjściowe  
 Dane wyjściowe transformacji to  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a>Zobacz także

- [Implementowanie procesora XSLT przy użyciu klasy XslTransform](xsltransform-class-implements-the-xslt-processor.md)
