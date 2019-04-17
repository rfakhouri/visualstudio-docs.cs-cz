---
title: Stránka události sestavení, Návrhář projektu (C#) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9d04c750bbe8183ae8e39765e41af2f138704ba3
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59654058"
---
# <a name="build-events-page-project-designer-c"></a>Stránka Události sestavení, návrhář projektu (C#)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Použití **události sestavení** stránku **Návrháře projektu** k určení pokyny ke konfiguraci sestavení. Můžete také zadat podmínky, za kterých jsou spuštěny žádné události po sestavení. Další informace najdete v tématu [jak: Určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)a [jak: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Konfigurace**  
 Tento ovládací prvek není na této stránce upravovat. Popis tohoto ovládacího prvku, naleznete v tématu [stránku sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Platforma**  
 Tento ovládací prvek není na této stránce upravovat. Popis tohoto ovládacího prvku, naleznete v tématu [stránku sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Příkazový řádek události před sestavením**  
 Určuje všechny příkazy se mají provést před začátkem sestavení. Zadejte dlouhé příkazy, klikněte na tlačítko **upravit před sestavením** zobrazíte [pre-build Event/po sestavení příkazového řádku dialogové okno události](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
>  Události před sestavením nebudou spuštěny, pokud je aktuální projekt a není aktivováno žádné sestavení.  
  
 **Příkazový řádek události po sestavení**  
 Určuje všechny příkazy k provedení po skončení sestavování. Zadejte dlouhé příkazy, klikněte na tlačítko **upravit POST-Build** zobrazíte **pre-build Event/po sestavení příkazového řádku dialogové okno události**.  
  
> [!NOTE]
>  Přidat `call` než vše post-build příkazy, které spouštějí soubory .bat. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Spustit událost po sestavení**  
 Následující podmínky pro událost po sestavení ke spuštění, určuje, jak je znázorněno v následující tabulce.  
  
|Možnost|Výsledek|  
|------------|------------|  
|**Vždy**|Událost po sestavení se spustí bez ohledu na to, zda byl sestaven úspěšně.|  
|**Při úspěšném sestavení**|Událost po sestavení spustí-li sestavení úspěšné. Díky tomu se událost se spustí i pro projekt, který je aktuální, tak dlouho, dokud sestavení úspěšné.|  
|**Když sestavení aktualizuje výstup projektu**|Událost po sestavení poběží pouze po kompilátoru výstupního souboru (.exe nebo .dll) se liší od předchozí výstupní soubor kompilátoru. Událost po sestavení se díky tomu se nespustil, když je aktuální projekt.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Postupy: Určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)   
 [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)   
 [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)
