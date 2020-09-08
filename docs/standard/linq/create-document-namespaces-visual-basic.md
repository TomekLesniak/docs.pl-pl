---
title: Jak utworzyć dokument z przestrzeniami nazw w Visual Basic-LINQ to XML
description: Użyj literałów XML w Visual Basic, aby utworzyć dokumenty, które mają domyślne przestrzenie nazw lub przestrzenie nazw z prefiksem.
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: 48e2a1abf8f7a82df3db5cb2f580804d67776b15
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553507"
---
# <a name="how-to-create-a-document-with-namespaces-in-visual-basic-linq-to-xml"></a>Jak utworzyć dokument z przestrzeniami nazw w Visual Basic (LINQ to XML)

W tym artykule przedstawiono sposób tworzenia dokumentu z przestrzeniami nazw w Visual Basic.

W przypadku używania literałów XML w Visual Basic użytkownicy mogą definiować jedną globalną domyślną przestrzeń nazw XML. Ta przestrzeń nazw jest domyślną przestrzenią nazw dla literałów XML i właściwości XML. Domyślną przestrzeń nazw XML można zdefiniować na poziomie projektu lub na poziomie pliku. Jeśli jest on zdefiniowany na poziomie pliku, zastępuje domyślny obszar nazw na poziomie projektu.

Można również zdefiniować inne przestrzenie nazw i określić prefiksy przestrzeni nazw dla tych przestrzeni nazw. Użyj `Imports` słowa kluczowego, aby zdefiniować oba typy przestrzeni nazw.

Aby uzyskać więcej informacji, zobacz [literały XML w Visual Basic](xml-literals.md).

Należy zauważyć, że domyślna przestrzeń nazw XML dotyczy tylko elementów i nie do atrybutów. Atrybuty są domyślnie w domyślnym obszarze nazw. Można jednak użyć prefiksu przestrzeni nazw, aby umieścić atrybut w przestrzeni nazw.

## <a name="example-create-a-document-that-has-a-namespace"></a>Przykład: Tworzenie dokumentu, który ma przestrzeń nazw

Ten przykład tworzy dokument zawierający przestrzeń nazw.

```vb
Imports <xmlns:aw="http://www.adventure-works.com">
Module Module1
    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <aw:Child aw:Att="attvalue"/>
            </aw:Root>
        Console.WriteLine(root)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Child aw:Att="attvalue" />
</aw:Root>
```

## <a name="example-create-a-document-that-has-two-namespaces-one-with-a-prefix"></a>Przykład: Utwórz dokument zawierający dwie przestrzenie nazw, jeden z prefiksem

Ten przykład tworzy dokument zawierający dwie przestrzenie nazw. Jedna jest domyślną przestrzenią nazw, druga ma prefiks.

```vb
Imports <xmlns="http://www.adventure-works.com">
Imports <xmlns:fc="www.fourthcoffee.com">

Module Module1

    Sub Main()
        Dim root As XElement = _
            <Root>
                <Child Att="attvalue"/>
                <fc:Child2>child2 content</fc:Child2>
            </Root>
        Console.WriteLine(root)
    End Sub

End Module
```

Ten przykład generuje następujące wyniki:

```xml
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">
  <Child Att="attvalue" />
  <fc:Child2>child2 content</fc:Child2>
</Root>
```

## <a name="example-create-a-document-that-has-two-namespaces-both-with-prefixes"></a>Przykład: Utwórz dokument, który ma dwie przestrzenie nazw, zarówno z prefiksami

Poniższy przykład tworzy dokument zawierający dwie przestrzenie nazw, które mają prefiksy przestrzeni nazw.

Podczas serializowania drzewa XML LINQ to XML emituje deklaracje przestrzeni nazw zgodnie z wymaganiami, aby każdy element był w wyznaczeniu przestrzeni nazw.

```vb
Imports <xmlns:aw="http://www.adventure-works.com">
Imports <xmlns:fc="www.fourthcoffee.com">

Module Module1

    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <fc:Child>
                    <aw:DifferentChild>other content</aw:DifferentChild>
                </fc:Child>
                <aw:Child2>c2 content</aw:Child2>
                <fc:Child3>c3 content</fc:Child3>
            </aw:Root>
        Console.WriteLine(root)
    End Sub

End Module
```

Ten przykład generuje następujące wyniki:

```xml
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">
  <fc:Child>
    <aw:DifferentChild>other content</aw:DifferentChild>
  </fc:Child>
  <aw:Child2>c2 content</aw:Child2>
  <fc:Child3>c3 content</fc:Child3>
</aw:Root>
```

## <a name="see-also"></a>Zobacz też

- [Przegląd przestrzeni nazw](namespaces-overview.md)
