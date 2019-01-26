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
ms.prod: visual-studio-dev15
ms.openlocfilehash: 54b4340fe72552f3287a5c6ebec55c9c9d326ac1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54932269"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Postupy: Nastavování atributů CLR v elementu
Vlastní atributy jsou speciální atributy, které lze přidat do domény prvky, tvary, konektory a diagramy. Můžete přidat všechny atributy, které dědí z `System.Attribute` třídy.

### <a name="to-add-a-custom-attribute"></a>Chcete-li přidat vlastní atribut

1.  V **Průzkumník DSL**, vyberte požadovaný prvek, ke kterému chcete přidat vlastní atribut.

2.  V **vlastnosti** okna, další **vlastní atributy** vlastnosti, klikněte na tlačítko Procházet (**...** ) ikonu.

     **Upravit atributy** zobrazí se dialogové okno.

3.  V **název** sloupce, klikněte na tlačítko  **\<přidat atribut >** a zadejte název atributu. Stiskněte klávesu ENTER.

4.  Řádek pod názvem atributu zobrazuje závorky. Na tomto řádku zadejte typ parametru atributu (například `string`), a potom stiskněte klávesu ENTER.

5.  V **vlastnost Name** sloupce, zadejte vhodný název, například `MyString`.

6.  Klikněte na **OK**.

     **Vlastní atributy** vlastnost se nyní zobrazí atribut v následujícím formátu:

     `[` *AttributeName* `(` *ParameterName* `=` *typu* `)]`

## <a name="see-also"></a>Viz také

- [Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)