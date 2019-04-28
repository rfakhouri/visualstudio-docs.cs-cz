---
title: 'Postupy: Používání návrháře argumentů | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 90e259d9d5e71ab5e6837cc4aa9cd22ebf43aaac
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432367"
---
# <a name="how-to-use-the-argument-designer"></a>Postupy: Používání návrháře argumentů
Ve srovnání s předchozími verzemi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], Návrhář argumentů usnadňuje povolit datový tok do a z aktivity. Návrhář přistupuje po kliknutí **argumenty** tlačítko v levém dolním rohu návrhové plátno. Návrhář obsahuje seznam argumentů, které se zobrazí ve formě tabulky a může být řada seřazena podle všech záhlaví sloupců, s výjimkou **výchozí hodnota** sloupce. Každý argument obsahuje název, v/out/v – out/vlastnost směr, typ a výchozí hodnota výrazu (pokud existuje). Název a hodnota výrazu výchozí nejsou upravitelné textové pole a typu a směru jsou rozevírací seznamy. [!INCLUDE[crabout](../includes/crabout-md.md)] argumenty, naleznete v tématu [proměnné a argumenty](http://msdn.microsoft.com/library/d03dbe34-5b2e-4f21-8b57-693ee49611b8).  
  
### <a name="to-create-a-new-argument"></a>Chcete-li vytvořit nový argument  
  
1. Otevřete řešení pracovního postupu nebo aktivity v [!INCLUDE[vs2010](../includes/vs2010-md.md)].  
  
2. Otevřít návrhář argumentů kliknutím **argumenty** tlačítko v levém dolním rohu návrhové plátno. Zobrazí se Návrhář argumentů.  
  
3. Klikněte na prázdný řádek označený **vytvořit Argument**. Tím se přidá nový řádek s argumentem nové pomocí následující výchozí hodnoty: argumentx pro **název** tam, kde x je celé číslo s počáteční hodnotou 1, které je automatický navýšeno vytvořit argument jedinečné názvy **v**  pro **směr**, a **řetězec** pro **typ argumentu**. Přidá se žádná hodnota pro **výchozí hodnota**. Tyto hodnoty můžete změnit kdykoli během procesu návrhu pracovního postupu.  
  
    > [!NOTE]
    > Pokud chcete odstranit argument, argument kliknutím vyberte a stiskněte klávesu **odstranit** klíč.  
  
## <a name="see-also"></a>Viz také  
 [Návrhář postupu provádění](../workflow-designer/using-the-workflow-designer.md)   
 [Proměnné a argumenty](http://msdn.microsoft.com/library/d03dbe34-5b2e-4f21-8b57-693ee49611b8)