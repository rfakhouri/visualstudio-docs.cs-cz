---
title: "Postupy: použití Vizualizéru stromu WPF | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: 2a1bf1cd-90f9-4d06-9fb4-1bfc925afef3
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e30d1fbd8cd23a514d1036bc43c809626c665d73
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-the-wpf-tree-visualizer"></a>Postupy: Použití vizualizéru stromu WPF
Můžete vizualizéru stromu WPF a prozkoumejte vizuálním stromu WPF objektu a zobrazte vlastnosti závislosti WPF pro objekty, které jsou obsaženy ve stromové struktuře. Další informace o visual stromy najdete v tématu [stromy v grafickém subsystému WPF](/dotnet/framework/wpf/advanced/trees-in-wpf). Další informace o vlastnostech závislostí v tématu [přehled vlastností závislostí](/dotnet/framework/wpf/advanced/dependency-properties-overview).  
  
 Když otevřete vizualizéru stromu WPF, zobrazí se dvě podokna: **vizuálním stromu** na levé straně a **vlastnosti** *název***:**  *Typ* podokně na pravé straně. Vyberte libovolný objekt v **vizuálním stromu** podokně a **vlastnosti** *název***:***typu* se podokno Zobrazit vlastnosti pro tento objekt automaticky aktualizuje.  
  
### <a name="to-open-the-wpf-tree-visualizer"></a>Chcete-li otevřít vizualizéru stromu WPF  
  
1.  V popis dat **sledovat** okně **automobily** okno, nebo **místní hodnoty –** okno vedle názvu objektu WPF klikněte na šipku vedle ikonu lupy.  
  
     Zobrazí se seznam vizualizérech.  
  
2.  Klikněte na tlačítko **Vizualizéru stromu WPF**.  
  
### <a name="to-search-the-visual-tree"></a>K vyhledání vizuálním stromu  
  
-   V **vizuálním stromu** podokně zadejte řetězec, kterou chcete hledat v **vyhledávání** pole.  
  
     První objekt vizualizéru stromu WPF okamžitě vyhledá ve vizuálním stromu, který odpovídá řetězec, který jste zadali. Zadejte více znaků se najít přesnější shodu.  
  
    -   Chcete-li přejít na další shodu v rámci stromu visual, klikněte na tlačítko **Další**.  
  
    -   Chcete-li vrátit k předchozí shodě, klikněte na tlačítko **Prev**.  
  
    -   Zrušte kritéria hledání, klikněte na tlačítko **vymazat**.  
  
### <a name="to-search-the-properties-list"></a>Pro seznam vlastností vyhledávání  
  
-   V **vlastnosti** *název***:***typ* podokně zadejte řetězec, vaše chcete hledat v **filtrovat**pole.  
  
     Vizualizéru stromu WPF okamžitě vyhledá vlastnosti, které odpovídají řetězec, který jste zadali; v seznamu se nyní zobrazí pouze vlastnosti odpovídající řetězec, který jste zadali. Zadejte více znaků se najít přesnější shodu.  
  
    -   Zrušte kritéria hledání, klikněte na tlačítko **vymazat**.  
  
### <a name="to-close-the-visualizer"></a>Zavřete vizualizéru  
  
-   Klikněte **Zavřít** ikonu v pravém horním rohu dialogu.  
  
## <a name="see-also"></a>Viz také  
 [Vytvořit vlastní Vizualizérech](../debugger/create-custom-visualizers-of-data.md)   
 [Stromy v grafickém subsystému WPF](/dotnet/framework/wpf/advanced/trees-in-wpf)   
 [Přehled vlastností závislostí](/dotnet/framework/wpf/advanced/dependency-properties-overview)