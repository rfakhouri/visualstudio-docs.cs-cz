---
title: Formátování, XML, Textový editor, dialogové okno Možnosti
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
ms.assetid: bb539b3a-027c-4b2f-906e-403e0e22ba8d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 05ddfcb0613dac08fb6e4323062f87475bd8f0d1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53938589"
---
# <a name="formatting-xml-text-editor-options-dialog-box"></a>Formátování, XML, textový editor, dialogové okno Možnosti

Toto dialogové okno umožňuje zadat nastavení formátování pro Editor XML. Můžete přistupovat **možnosti** dialogové **nástroje** nabídky.

> [!NOTE]
> Tato nastavení jsou k dispozici, když vyberete **textový Editor** složky, **XML** složky a pak **formátování** možnost **možnosti** dialogové okno.

## <a name="attributes"></a>Atributy
 **Zachovat ruční formátování atributu**

 Atributy nejsou přeformátovány. Toto nastavení je výchozí.

> [!NOTE]
> Pokud jsou atributy na více řádcích, editoru odsazení každý řádek atributů tak, aby odpovídaly odsazení nadřazeného elementu.

 **Zarovnávat atributy na vlastním řádku**

 Zarovná druhého a dalších atributů svisle tak, aby odpovídaly odsazení prvního atributu. Následující text XML je příkladem jak by mělo být zarovnáno atributy.

```xml
<item id = "123-A"
      name = "hammer"
      price = "9.95">
</item>
```

## <a name="auto-reformat"></a>Automaticky přeformátovat
 **Při vložení ze schránky**

 Přeformátuje text XML vložené ze schránky.

 **Dokončení koncové značky**

 Element přeformátuje po dokončení koncová značka.

## <a name="mixed-content"></a>Smíšený obsah
 **Zachovat smíšený obsah ve výchozím nastavení**

 Určuje, zda editor přeformátuje smíšený obsah. Ve výchozím nastavení, pokusí opakovaně formátovat smíšený obsah, s výjimkou případů, kdy se obsah nachází v editoru `xml:space="preserve"` oboru.

 Pokud prvek obsahuje kombinaci textu a kódu, obsah jsou považovány za být smíšený obsah. Následuje příklad prvku se smíšeným obsahem.

```xml
<dir>c:\data\AlphaProject\
  <file readOnly="false">test1.txt</file>
  <file readOnly="false">test2.txt</file>
</dir>
```

## <a name="see-also"></a>Viz také:

- [Vlastnosti dokumentu XML, okno Vlastnosti](../xml-tools/xml-document-properties-properties-window.md)
- [Součásti editoru XML](../xml-tools/xml-editor-components.md)