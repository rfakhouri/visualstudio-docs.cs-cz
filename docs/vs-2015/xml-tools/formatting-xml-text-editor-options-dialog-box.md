---
title: Formátování, XML, textový Editor, dialogové okno Možnosti | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: bb539b3a-027c-4b2f-906e-403e0e22ba8d
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34eedf61afd79570ca1e4ba471efa9802aae7bfa
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59664122"
---
# <a name="formatting-xml-text-editor-options-dialog-box"></a>Formátování, XML, Textový editor, dialogové okno Možnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
