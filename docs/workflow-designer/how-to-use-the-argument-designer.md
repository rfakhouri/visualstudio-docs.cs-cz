---
title: "Postupy: používání Argument Designer | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
caps.latest.revision: "16"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5093e5561140a0ebff57da1f7c21a8954ee58bb3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-use-the-argument-designer"></a>Postupy: používání Argument Designer
Ve srovnání s předchozí verzí technologie [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], argument designer usnadňuje povolit datový tok do a z aktivity. Návrhář přistupuje kliknutím **argumenty** tlačítko v levém horním rohu na plátno návrhu. Návrhář obsahuje seznam argumentů, které jsou uvedeny ve formě tabulky a lze seřadit podle jednotlivých záhlaví sloupců, s výjimkou **výchozí hodnota** sloupce. Všechny argumenty obsahuje název, směr v nebo na více systémů/v – out nebo vlastnost, typ a výchozí hodnota výrazu (pokud existuje). Název a výchozí hodnota výrazu jsou upravitelných textových polí a typu a směr jsou rozevírací seznamy. [! ZAHRNOUT[crabout](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).  
  
### <a name="to-create-a-new-argument"></a>Chcete-li vytvořit nový argument  
  
1.  Otevřete řešení pracovního postupu nebo aktivity v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].  
  
2.  Otevřít návrhář argumenty kliknutím **argumenty** tlačítko v levém horním rohu na plátno návrhu. Návrhář argumenty se zobrazí.  
  
3.  Klikněte na prázdný řádek označený **vytvořit Argument**. Přidá nový řádek s argumentem nové pomocí následující výchozí hodnoty: argumentx pro **název** tam, kde x je celočíselná a má počáteční hodnotu 1, který se automaticky zvýší vytvořit jedinečný argument, **v**  pro **směr**, a **řetězec** pro **typ argumentu**. Přidá se žádná hodnota pro **výchozí hodnota**. Tyto hodnoty můžete změnit kdykoli během procesu návrhu pracovního postupu.  
  
    > [!NOTE]
    >  Pokud chcete odstranit argument, kliknutím vyberte argument a potom stiskněte klávesu **odstranit** klíč.  
  
## <a name="see-also"></a>Viz také  
 [Pomocí návrháře pracovních postupů](../workflow-designer/using-the-workflow-designer.md)   
 [Proměnné a argumenty](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)