---
title: "Postupy: zobrazení, uložit a konfigurace souborů protokolu sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75d38b76-26d6-4f43-bbe7-cbacd7cc81e7
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1a57911b8736af27caf0bd9ba30e9e03bdebed2d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-save-and-configure-build-log-files"></a>Postupy: Zobrazování, ukládání a konfigurace souborů protokolu sestavení
Jakmile vytvoříte projekt sady Visual Studio IDE, můžete zobrazit informace o toto sestavení v **výstup** okno. Pomocí těchto informací můžete, například řešit selhání sestavení. Pro projekty C++ můžete také zobrazit stejné informace v souboru .txt, který má vytvořili a uložili automaticky. Pro projekty spravovaného kódu, můžete zkopírovat a vkládat informace z **výstup** okno na .txt souboru a uložte ho sami. Prostředí IDE můžete také použít k určení toho, jaké typy informací, které chcete zobrazit o každé sestavení.  
  
 Pokud vytvoříte jakýkoli typ projekt pomocí nástroje MSBuild, můžete vytvořit soubor .txt se uložit informace o sestavení. Další informace najdete v tématu [získání sestavení protokoly](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
### <a name="to-view-the-build-log-file-for-a-c-project"></a>Chcete-li zobrazit v souboru protokolu sestavení projektu jazyka C++  
  
1.  V **Průzkumníka Windows** nebo **Průzkumníka souborů**, otevřete následující soubor: \\...\Visual Studio *verze*\Projects\\  *Název projektu*\\*ProjectName*\Debug\\*ProjectName*.txt  
  
### <a name="to-create-a-build-log-file-for-a-managed-code-project"></a>Chcete-li vytvořit soubor protokolu sestavení pro projekt spravovaného kódu  
  
1.  Na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
2.  V **výstup** okně informace z buildu zvýrazněte a zkopírujte jej do schránky.  
  
3.  Otevřete textový editor, například Poznámkový blok, vložte informace do souboru a pak ho uložte.  
  
### <a name="to-change-the-amount-of-information-included-in-the-build-log"></a>Chcete-li změnit množství informací, které jsou součástí protokolu sestavení  
  
1.  Na řádku nabídek zvolte **nástroje**, **možnosti**.  
  
2.  Na **projekty a řešení** vyberte **sestavit a spustit** stránky.  
  
3.  V **výstup sestavení projektu MSBuild podrobností** seznam, vyberte jednu z následujících hodnot a potom zvolte **OK** tlačítko.  
  
    |Úroveň podrobností|Popis|  
    |---------------------|-----------------|  
    |Quiet|Zobrazí souhrn pouze sestavení.|  
    |minimální|Zobrazí souhrn sestavení a chyby, upozornění a zprávy, které jsou klasifikovány jako vysoce důležité.|  
    |Normální|Zobrazí souhrn sestavení; chyby, upozornění a zprávy, které jsou klasifikovány jako vysoce důležité. a hlavní kroky sestavení. Nejčastěji budete používat tato úroveň podrobností.|  
    |Podrobné|Zobrazí souhrn sestavení; chyby, upozornění a zprávy, které jsou klasifikovány jako vysoce důležité. všechny kroky sestavení; zprávy, které jsou klasifikovány od normální důležitosti a.|  
    |Diagnostika|Zobrazí všechna data, která je k dispozici pro sestavení. Tato úroveň podrobností můžete pomoci při ladění problémů s vlastní sestavovací skripty a další potíže sestavení.|  
  
     Další informace najdete v tématu [dialogové okno Možnosti, projekty a řešení, sestavení a spuštění](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md) a <xref:Microsoft.Build.Framework.LoggerVerbosity>.  
  
    > [!IMPORTANT]
    >  Je nutné znovu sestavit projekt pro vaše změny se projeví **výstup** okno (všechny projekty) a *ProjectName*souboru .txt (pouze projekty C++).  
  
## <a name="see-also"></a>Viz také  
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Sestavování a čištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)