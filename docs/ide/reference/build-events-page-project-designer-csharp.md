---
title: Stránka události sestavení, Návrhář projektu (C#) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: ec7aa70db8ca2f4fc4ea8f0a4a06fc35857be27b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="build-events-page-project-designer-c"></a>Stránka Události sestavení, návrhář projektu (C#)
Použití **události sestavení** stránky **Návrhář projektu** k určení pokyny ke konfiguraci sestavení. Můžete také zadat podmínky, za kterých se spustit žádné události po sestavení. Další informace najdete v tématu [postupy: určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)a [postup: Zadejte události sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Konfigurace**  
 Tento ovládací prvek se nedá upravovat na této stránce. Popis tohoto ovládacího prvku naleznete v tématu [stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Platforma**  
 Tento ovládací prvek se nedá upravovat na této stránce. Popis tohoto ovládacího prvku naleznete v tématu [stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Příkazový řádek události před sestavením**  
 Určuje všechny příkazů pro spuštění před zahájením sestavení. Chcete-li typ dlouho příkazy, klikněte na tlačítko **upravit před sestavením** zobrazíte [před sestavením událostí/po sestavení příkazového řádku dialogové okno události](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
>  Události před sestavením se nespustí, pokud je aktuální projekt a není aktivováno žádné sestavení.  
  
 **Události po sestavení příkazového řádku**  
 Určuje žádné příkazy k provedení po skončení sestavování. Chcete-li typ dlouho příkazy, klikněte na tlačítko **upravit po sestavení** zobrazíte **před sestavením událostí/po sestavení příkazového řádku dialogové okno události**.  
  
> [!NOTE]
>  Přidat `call` příkaz před příkazy všechny po sestavení, které spouštějí .bat soubory. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Spustit události po sestavení**  
 Následující podmínky pro události po sestavení ke spuštění, určuje, jak je znázorněno v následující tabulce.  
  
|Možnost|Výsledek|  
|------------|------------|  
|**Vždy**|Události po sestavení se spustí bez ohledu na to, jestli sestavení úspěšné.|  
|**V úspěšném sestavení**|Události po sestavení se spustí, pokud sestavení úspěšné. Proto událost se spustí i pro projekt, který je aktuální, tak dlouho, dokud sestavení úspěšné.|  
|**Při sestavení aktualizace výstup projektu**|Události po sestavení se spustí, pouze pokud se liší od předchozí výstupního souboru kompilátoru kompilátoru výstupní soubor (.exe nebo .dll). Události po sestavení není proto spustit, pokud je aktuální projekt.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Postupy: určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)   
 [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)   
 [Kompilace a sestavení](../../ide/compiling-and-building-in-visual-studio.md)