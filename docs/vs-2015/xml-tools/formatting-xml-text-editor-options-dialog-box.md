---
title: Formátování, XML, textový Editor, dialogové okno Možnosti | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb539b3a-027c-4b2f-906e-403e0e22ba8d
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 352a43cbe16540f1b231077bb1b7c23dd45ffcec
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631598"
---
# <a name="formatting-xml-text-editor-options-dialog-box"></a>Formátování, XML, Textový editor, dialogové okno Možnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [formátování, XML, textový Editor, dialogové okno Možnosti](https://docs.microsoft.com/visualstudio/xml-tools/formatting-xml-text-editor-options-dialog-box).  
  
  
Toto dialogové okno umožňuje zadat nastavení formátování pro Editor XML. Můžete přistupovat **možnosti** dialogové **nástroje** nabídky.  
  
> [!NOTE]
>  Tato nastavení jsou k dispozici, když vyberete **textový Editor** složky, **XML** složky a pak **formátování** možnost **možnosti** dialogové okno.  
  
## <a name="attributes"></a>Atributy  
 **Zachovat ruční formátování atributu**  
 Atributy nejsou přeformátovány. Toto nastavení je výchozí.  
  
> [!NOTE]
>  Pokud jsou atributy na více řádcích, editoru odsazení každý řádek atributů tak, aby odpovídaly odsazení nadřazeného elementu.  
  
 **Zarovnávat atributy na vlastním řádku**  
 Zarovná druhého a dalších atributů svisle tak, aby odpovídaly odsazení prvního atributu. Následující text XML je příkladem jak by mělo být zarovnáno atributy.  
  
```  
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
  
```  
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
</dir>  
```  
  
## <a name="see-also"></a>Viz také  
 [Vlastnosti dokumentu XML, okno Vlastnosti](../xml-tools/xml-document-properties-properties-window.md)   
 [Součásti editoru XML](../xml-tools/xml-editor-components.md)



