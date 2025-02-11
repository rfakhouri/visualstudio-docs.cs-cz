---
title: Dialogové okno události (Visual Basic) sestavení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- build events, specifying
- pre-build events
- Build Events dialog box
- post-build events
ms.assetid: 3a81a7c7-39f9-47a8-ba5a-b351227f380e
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5eb4473056e8d9c42fedf781ed0f5d1189f42fca
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442662"
---
# <a name="build-events-dialog-box-visual-basic"></a>Dialogové okno Události sestavení (Visual Basic)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Použití **události sestavení** dialogové okno k zadání pokyny ke konfiguraci sestavení. Můžete také zadat podmínky, za kterých jsou spuštěny žádné události před sestavením nebo po sestavení. Další informace najdete v tématu [jak: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
 **Příkazový řádek události před sestavením**  
 Určuje všechny příkazy se mají provést před začátkem sestavení. Zadejte dlouhé příkazy, klikněte na tlačítko **upravit před sestavením** zobrazíte [pre-build Event/po sestavení příkazového řádku dialogové okno události](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
> Události před sestavením nebudou spuštěny, pokud je aktuální projekt a není aktivováno žádné sestavení.  
  
 **Příkazový řádek události po sestavení**  
 Určuje všechny příkazy k provedení po skončení sestavování. Zadejte dlouhé příkazy, klikněte na tlačítko **upravit POST-Build** zobrazíte **události před sestavením události/po sestavení příkazového řádku d**ialog pole.  
  
> [!NOTE]
> Přidat `call` než vše post-build příkazy, které spouštějí soubory .bat. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Spustit událost po sestavení**  
 Podmínky pro událost po sestavení ke spuštění, určuje, jak je znázorněno v následující tabulce.  
  
|Možnost|Výsledek|  
|------------|------------|  
|**Vždy**|Událost po sestavení se spustí bez ohledu na to, zda byl sestaven úspěšně.|  
|**Při úspěšném sestavení**|Událost po sestavení spustí-li sestavení úspěšné. Událost se spustí i pro projekt, který je aktuální, tak dlouho, dokud sestavení úspěšné. Toto je výchozí nastavení.|  
|**Když sestavení aktualizuje výstup projektu**|Událost po sestavení spustí pouze v případě, že kompilátoru výstupního souboru (.exe nebo .dll) se liší od předchozí výstupní soubor kompilátoru. Pokud je aktuální projekt není spuštěna událost po sestavení.|  
  
## <a name="see-also"></a>Viz také  
 [Stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Postupy: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Dialogové okno Příkazový řádek události před sestavením / po sestavení](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)
