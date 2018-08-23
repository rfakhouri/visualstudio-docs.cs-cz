---
title: 'Postupy: používání návrháře argumentů | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: eaff53dc04c0ad2367147ae91c7de756e5ca4366
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668197"
---
# <a name="how-to-use-the-argument-designer"></a>Postupy: používání návrháře argumentů
Ve srovnání s předchozími verzemi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], Návrhář argumentů usnadňuje povolit datový tok do a z aktivity. Návrhář přistupuje po kliknutí **argumenty** tlačítko v levém dolním rohu návrhové plátno. Návrhář obsahuje seznam argumentů, které se zobrazí ve formě tabulky a může být řada seřazena podle všech záhlaví sloupců, s výjimkou **výchozí hodnota** sloupce. Každý argument obsahuje název, v/out/v – out/vlastnost směr, typ a výchozí hodnota výrazu (pokud existuje). Název a hodnota výrazu výchozí nejsou upravitelné textové pole a typu a směru jsou rozevírací seznamy. [!INCLUDE[crabout](../includes/crabout-md.md)] argumenty, naleznete v tématu [proměnné a argumenty](http://msdn.microsoft.com/library/d03dbe34-5b2e-4f21-8b57-693ee49611b8).  
  
### <a name="to-create-a-new-argument"></a>Chcete-li vytvořit nový argument  
  
1.  Otevřete řešení pracovního postupu nebo aktivity v [!INCLUDE[vs2010](../includes/vs2010-md.md)].  
  
2.  Otevřít návrhář argumentů kliknutím **argumenty** tlačítko v levém dolním rohu návrhové plátno. Zobrazí se Návrhář argumentů.  
  
3.  Klikněte na prázdný řádek označený **vytvořit Argument**. Tím se přidá nový řádek s argumentem nové pomocí následující výchozí hodnoty: argumentx pro **název** tam, kde x je celé číslo s počáteční hodnotou 1, které je automatický navýšeno vytvořit argument jedinečné názvy **v**  pro **směr**, a **řetězec** pro **typ argumentu**. Přidá se žádná hodnota pro **výchozí hodnota**. Tyto hodnoty můžete změnit kdykoli během procesu návrhu pracovního postupu.  
  
    > [!NOTE]
    >  Pokud chcete odstranit argument, argument kliknutím vyberte a stiskněte klávesu **odstranit** klíč.  
  
## <a name="see-also"></a>Viz také  
 [Návrhář postupu provádění](../workflow-designer/using-the-workflow-designer.md)   
 [Proměnné a argumenty](http://msdn.microsoft.com/library/d03dbe34-5b2e-4f21-8b57-693ee49611b8)