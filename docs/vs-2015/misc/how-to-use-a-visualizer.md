---
title: 'Postupy: použití Vizualizéru | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.dataviewer
- vs.debug.stringviewer
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers, about visualizers
ms.assetid: d2611385-0134-4387-8c5a-979fe625a462
caps.latest.revision: 37
ms.author: susanno
manager: douge
ms.openlocfilehash: cc158e0d84db56bc26262d60acd0fb8e92e47188
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673014"
---
# <a name="how-to-use-a-visualizer"></a>Postupy: Použití vizualizéru
Chcete-li zobrazit obsah proměnné nebo objektu způsobem, který má smysl pro typ dat můžete použít vizualizéru. Můžete použít vizualizéry z **DataTips**, **Watch** okna, **automatické hodnoty** okna, nebo **místní hodnoty** okno.  
  
 Vizualizéry nepodporuje Compact Framework.  
  
> [!NOTE]
>  V **Store** aplikací, jenom standardní text, HTML, XML a JSON vizualizéry jsou podporovány. Vizualizéry vlastní (uživatelem vytvořené) nejsou podporovány.  
  
### <a name="to-open-a-visualizer"></a>Chcete-li otevřít vizualizéru  
  
1.  Klikněte na ikonu lupy, které se zobrazí vedle názvu proměnné v **DataTips**, **Watch** okna, nebo **automatické hodnoty**, **místních hodnot**, nebo **Rychlé kukátko** okna.  
  
     Zobrazí se seznam vizualizéry.  
  
2.  Klikněte na vizualizaci, kterou chcete použít.  
  
### <a name="to-use-a-visualizer-for-managed-code-during-remote-debugging"></a>Použití vizualizéru během vzdálené ladění pro spravovaný kód  
  
-   Zkopírujte vizualizéru knihovny DLL ke vzdálenému počítači před spuštěním ladicí relace.  
  
     Cesta k souboru DLL musí být stejná na vzdálené i místní počítače. Tento způsob může být buď z následujících umístění:  
  
     *Cesta pro instalaci aplikace Visual Studio* `\Common7\Packages\Debugger\Visualizers`  
  
     -nebo-  
  
     `My Documents\Visual Studio 2010\Visualizers` *Verze sady Visual Studio* `\Visualizers`  
  
## <a name="see-also"></a>Viz také  
 [Vytváření vlastních Vizualizérů](../debugger/create-custom-visualizers-of-data.md)   
 [Postupy: instalace Vizualizéru](../debugger/how-to-install-a-visualizer.md)   
 [Postupy: zápis Vizualizéru](../debugger/how-to-write-a-visualizer.md)   
 [Zobrazení hodnot dat v datových tipech](../debugger/view-data-values-in-data-tips-in-the-code-editor.md)