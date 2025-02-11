---
title: Options, Text Editor, XML, Formatting
ms.date: 10/29/2018
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Formatting
ms.assetid: 203e60b2-7b80-4ff4-9fa1-aa9f4374377b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e20b2f7ebe351aa050ea66468fb33aba8e4a31bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62969264"
---
# <a name="options-text-editor-xml-formatting"></a>Options, Text Editor, XML, Formatting

Použití **formátování** stránky možnosti můžete zadat způsob formátování elementů a atributů v dokumentech XML. Chcete-li získat přístup k XML možnosti formátování, zvolte **nástroje** > **možnosti** > **textový Editor** > **XML**a klikněte na tlačítko **formátování**.

## <a name="attributes"></a>Atributy

**Zachovat ruční formátování atributu**

Nelze přeformátovat atributy. Toto nastavení je výchozí hodnota.

> [!NOTE]
> Pokud jsou atributy na více řádcích, editoru odsazení každý řádek atributů tak, aby odpovídaly odsazení nadřazeného elementu.

**Zarovnávat atributy na samostatné řádky**

Zarovnejte atributy druhé a následné svisle tak, aby odpovídaly odsazení prvního atributu. Následující text XML je příkladem jak by mělo být zarovnáno atributy:

```xml
<item id = "123-A"
      name = "hammer"
      price = "9.95">
</item>
```

## <a name="auto-reformat"></a>Automaticky přeformátovat

**Při vložení ze schránky**

U vydavatelských text XML vložené ze schránky.

**Dokončení koncové značky**

Po dokončení koncovou značku u vydavatelských elementu.

## <a name="mixed-content"></a>Smíšený obsah

**Formátovat smíšený obsah ve výchozím nastavení.**

Pokusí se opakovaně formátovat smíšený obsah, s výjimkou případů, kdy se obsah nachází v `xml:space="preserve"` oboru. Toto nastavení je výchozí hodnota.

Pokud prvek obsahuje kombinaci textu a kódu, obsah jsou považovány za být smíšený obsah. Tady je příklad elementu se smíšeným obsahem.

```xml
<dir>c:\data\AlphaProject\
  <file readOnly="false">test1.txt</file>
  <file readOnly="false">test2.txt</file>
</dir>
```

## <a name="see-also"></a>Viz také:

- [Možnosti XML – různé](options-text-editor-xml-miscellaneous.md)
- [Nástroje XML v sadě Visual Studio](../../xml-tools/xml-tools-in-visual-studio.md)