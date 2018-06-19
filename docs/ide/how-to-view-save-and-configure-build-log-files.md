---
title: 'Postupy: zobrazení, uložit a konfigurace souborů protokolu sestavení | Microsoft Docs'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
ms.assetid: 75d38b76-26d6-4f43-bbe7-cbacd7cc81e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1888e2244182296ad2c5375d0055583dda69e592
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31944970"
---
# <a name="how-to-view-save-and-configure-build-log-files"></a>Postupy: zobrazení, uložit a konfigurace souborů protokolu sestavení

Jakmile vytvoříte projekt sady Visual Studio IDE, můžete zobrazit informace o toto sestavení v **výstup** okno. Pomocí těchto informací můžete, například řešit selhání sestavení. Projekty C++, můžete také zobrazit stejné informace ve *.txt* soubor, který má vytvořili a uložili automaticky. Pro projekty spravovaného kódu, můžete zkopírovat a vkládat informace z **výstup** okno na *.txt* souboru a uložte ho sami. Prostředí IDE můžete také použít k určení toho, jaké typy informací, které chcete zobrazit o každé sestavení.

Pokud vytvoříte jakýkoli typ projekt pomocí nástroje MSBuild, můžete vytvořit *.txt* soubor uložte informace o sestavení. Další informace najdete v tématu [získat sestavení protokoly](../msbuild/obtaining-build-logs-with-msbuild.md).

## <a name="to-view-the-build-log-file-for-a-c-project"></a>Chcete-li zobrazit v souboru protokolu sestavení projektu jazyka C++

1.  V **Průzkumníka Windows** nebo **Průzkumníka souborů**, otevřete následující soubor:  *\\...\Visual Studio \<verze\>\Projects\\ < název projektu\>\\< název projektu\>\Debug\\< název projektu\>.txt*

## <a name="to-create-a-build-log-file-for-a-managed-code-project"></a>Chcete-li vytvořit soubor protokolu sestavení pro projekt spravovaného kódu

1.  Na řádku nabídek zvolte **sestavení** > **sestavit řešení**.

2.  V **výstup** okno, zvýrazněte informace z buildu a potom ho zkopírujete do **schránky**.

3.  Otevřete textový editor, například **Poznámkový blok**, příslušné informace vložte do souboru a pak ho uložte.

## <a name="to-change-the-amount-of-information-included-in-the-build-log"></a>Chcete-li změnit množství informací, které jsou součástí protokolu sestavení

1.  Na řádku nabídek zvolte **nástroje** > **možnosti**.

2.  Na **projekty a řešení** vyberte **sestavit a spustit** stránky.

3.  V **výstup sestavení projektu MSBuild podrobností** seznam, vyberte jednu z následujících hodnot a potom zvolte **OK** tlačítko.

    |Úroveň podrobností|Popis|
    |---------------------|-----------------|
    |**quiet**|Zobrazí souhrn pouze sestavení.|
    |**minimální**|Zobrazí souhrn sestavení a chyby, upozornění a zprávy, které jsou klasifikovány jako vysoce důležité.|
    |**Normální**|Zobrazí souhrn sestavení; chyby, upozornění a zprávy, které jsou klasifikovány jako vysoce důležité. a hlavní kroky sestavení. Nejčastěji budete používat tato úroveň podrobností.|
    |**Podrobné**|Zobrazí souhrn sestavení; chyby, upozornění a zprávy, které jsou klasifikovány jako vysoce důležité. všechny kroky sestavení; zprávy, které jsou klasifikovány od normální důležitosti a.|
    |**Diagnostika**|Zobrazí všechna data, která je k dispozici pro sestavení. Tato úroveň podrobností můžete pomoci při ladění problémů s vlastní sestavovací skripty a další potíže sestavení.|

     Další informace najdete v tématu [dialogové okno Možnosti, projekty a řešení, sestavení a spuštění](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md) a <xref:Microsoft.Build.Framework.LoggerVerbosity>.

    > [!IMPORTANT]
    > Je nutné znovu sestavit projekt pro vaše změny se projeví **výstup** okno (všechny projekty) a  *<ProjectName>.txt* souboru (pouze C++ projekty).

## <a name="see-also"></a>Viz také

- [Získání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)
- [Sestavení a čištění projektů a řešení v sadě Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)