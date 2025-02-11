---
title: 'Postupy: Nastavování atributů CLR v elementu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8954aa6a42e743617080bb6918508273c1dd9528
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62811274"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Postupy: Nastavování atributů CLR v elementu
Vlastní atributy jsou speciální atributy, které lze přidat do domény prvky, tvary, konektory a diagramy. Můžete přidat všechny atributy, které dědí z `System.Attribute` třídy.

### <a name="to-add-a-custom-attribute"></a>Chcete-li přidat vlastní atribut

1. V **Průzkumník DSL**, vyberte požadovaný prvek, ke kterému chcete přidat vlastní atribut.

2. V **vlastnosti** okna, další **vlastní atributy** vlastnosti, klikněte na tlačítko Procházet ( **...** ) ikonu.

     **Upravit atributy** zobrazí se dialogové okno.

3. V **název** sloupce, klikněte na tlačítko  **\<přidat atribut >** a zadejte název atributu. Stiskněte klávesu ENTER.

4. Řádek pod názvem atributu zobrazuje závorky. Na tomto řádku zadejte typ parametru atributu (například `string`), a potom stiskněte klávesu ENTER.

5. V **vlastnost Name** sloupce, zadejte vhodný název, například `MyString`.

6. Klikněte na **OK**.

     **Vlastní atributy** vlastnost se nyní zobrazí atribut v následujícím formátu:

     `[` *AttributeName* `(` *ParameterName* `=` *typu* `)]`

## <a name="see-also"></a>Viz také

- [Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)