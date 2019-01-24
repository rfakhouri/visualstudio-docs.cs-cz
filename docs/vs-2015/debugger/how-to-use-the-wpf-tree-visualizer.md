---
title: 'Postupy: Použití Vizualizéru stromu WPF | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: 2a1bf1cd-90f9-4d06-9fb4-1bfc925afef3
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6d2fc99235c9001cd465236c82588e33a842c168
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54794754"
---
# <a name="how-to-use-the-wpf-tree-visualizer"></a>Postupy: Použití vizualizéru stromu WPF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vizualizéru stromu WPF můžete použít k prozkoumání vizuálního stromu WPF objektu a chcete-li zobrazit vlastnosti závislosti WPF pro objekty, které jsou obsaženy ve stromové struktuře. Další informace o vizuální stromové struktury, naleznete v tématu [stromy v subsystému WPF](http://msdn.microsoft.com/library/e83f25e5-d66b-4fc7-92d2-50130c9a6649). Další informace o vlastnosti závislosti, naleznete v tématu [přehled vlastností závislosti](http://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5).  
  
 Když otevřete vizualizéru stromu WPF, zobrazí se dvě podokna: **vizuální strom** na levé straně a **vlastnosti** _název_**:**  _Typ_ podokno na pravé straně. Vyberte libovolný objekt v **vizuální strom** podokně a **vlastnosti** _název_**:**_typ_ podokno automaticky aktualizuje a zobrazí vlastnosti pro tento objekt.  
  
### <a name="to-open-the-wpf-tree-visualizer"></a>Chcete-li otevřít vizualizéru stromu WPF  
  
1.  V datovém tipu **Watch** okně **automatické hodnoty** okna, nebo **lokální** okna vedle názvu objektu WPF, klikněte na šipku vedle ikony lupy.  
  
     Zobrazí se seznam vizualizéry.  
  
2.  Klikněte na tlačítko **Vizualizéru stromu WPF**.  
  
### <a name="to-search-the-visual-tree"></a>K vyhledání ve vizuálním stromu  
  
-   V **vizuální strom** podokně, zadejte řetězec, který chcete vyhledat v **hledání** pole.  
  
     První objekt vizualizéru stromu WPF okamžitě najde ve vizuálním stromu, který se shoduje s řetězcem, který jste zadali. Zadejte více znaků pro vyhledání více přesné shody.  
  
    -   Chcete-li přejít na další shodu v rámci vizuálního stromu, klikněte na tlačítko **Další**.  
  
    -   Chcete-li přejít zpět k předchozí shodě, klikněte na tlačítko **předchozí**.  
  
    -   Kritéria hledání, klikněte na **vymazat**.  
  
### <a name="to-search-the-properties-list"></a>Chcete-li hledat seznam vlastností  
  
-   V **vlastnosti** _název_**:**_typ_ podokně, zadejte řetězec chcete vyhledat v **filtrovat**pole.  
  
     Vizualizéru stromu WPF okamžitě vyhledá vlastnosti, které odpovídají řetězci, který jste zadali; Teď se v seznamu zobrazí pouze vlastnosti odpovídající řetězec, který jste zadali. Zadejte více znaků pro vyhledání shody přesnější.  
  
    -   Kritéria hledání, klikněte na **vymazat**.  
  
### <a name="to-close-the-visualizer"></a>Zavřít vizualizér  
  
-   Klikněte na tlačítko **Zavřít** ikonu v pravém horním rohu dialogového okna.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Použití Vizualizéru](../misc/how-to-use-a-visualizer.md)   
 [Vytváření vlastních Vizualizérů](../debugger/create-custom-visualizers-of-data.md)   
 [Stromy v subsystému WPF](http://msdn.microsoft.com/library/e83f25e5-d66b-4fc7-92d2-50130c9a6649)   
 [Přehled vlastností závislosti](http://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5)
