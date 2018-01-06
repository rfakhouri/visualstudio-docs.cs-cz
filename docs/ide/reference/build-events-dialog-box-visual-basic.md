---
title: "Dialogové okno události (Visual Basic) sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- build events, specifying
- pre-build events
- Build Events dialog box
- post-build events
ms.assetid: 3a81a7c7-39f9-47a8-ba5a-b351227f380e
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: da28d0858784a8e71006c0ec072c3aea5110037e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="build-events-dialog-box-visual-basic"></a>Dialogové okno Události sestavení (Visual Basic)
Použití **události sestavení** dialogové okno zadat pokyny ke konfiguraci sestavení. Můžete také zadat podmínky, za kterých se spustit žádné události před sestavením nebo po sestavení. Další informace najdete v tématu [postupy: určení události sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
 **Příkazový řádek události před sestavením**  
 Určuje všechny příkazů pro spuštění před zahájením sestavení. Chcete-li typ dlouho příkazy, klikněte na tlačítko **upravit před sestavením** zobrazíte [před sestavením událostí/po sestavení příkazového řádku dialogové okno události](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
>  Události před sestavením se nespustí, pokud je aktuální projekt a není aktivováno žádné sestavení.  
  
 **Události po sestavení příkazového řádku**  
 Určuje žádné příkazy k provedení po skončení sestavování. Chcete-li typ dlouho příkazy, klikněte na tlačítko **upravit po sestavení** zobrazíte **událost před sestavením událostí/po sestavení příkazového řádku d**ialog pole.  
  
> [!NOTE]
>  Přidat `call` příkaz před příkazy všechny po sestavení, které spouštějí .bat soubory. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Spustit události po sestavení**  
 Podmínky pro události po sestavení ke spuštění, určuje, jak je znázorněno v následující tabulce.  
  
|Možnost|Výsledek|  
|------------|------------|  
|**Vždy**|Události po sestavení se spustí bez ohledu na to, jestli sestavení úspěšné.|  
|**V úspěšném sestavení**|Události po sestavení se spustí, pokud sestavení úspěšné. Událost se spustí i pro projekt, který je aktuální, tak dlouho, dokud sestavení úspěšné. Toto je výchozí nastavení.|  
|**Při sestavení aktualizace výstup projektu**|Události po sestavení se spustí pouze v případě, že do kompilátoru výstupní soubor (.exe nebo .dll) se liší od předchozí výstupního souboru kompilátoru. Události po sestavení nespustí, pokud je aktuální projekt.|  
  
## <a name="see-also"></a>Viz také  
 [Stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Postupy: určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Dialogové okno Příkazový řádek události/po sestavení události před sestavením](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)