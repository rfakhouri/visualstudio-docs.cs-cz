---
title: 'Návrhář postupu provádění - postupy: vytváření stavu počítače pracovního postupu konzolových aplikací (zastaralé)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- console applications, state machine workflows
- state machine workflow console applications
- state machine workflows, console applicationa
ms.assetid: d6170b5d-5d4f-48e1-8257-c78604f27eac
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 805b048a9e30f7a637e178d223b962259dadd926
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-state-machine-workflow-console-applications-legacy"></a>Postupy: vytváření stavu počítače pracovního postupu konzolových aplikací (zastaralé)

Postupujte podle těchto kroků k vytvoření projektu konzolové aplikace stavu počítače pracovního postupu pomocí starší verze zadaná v Návrháři pracovních postupů Windows pomocí sady Visual Studio 2010. Pokud budete potřebovat cílit na rozhraní .NET Framework verze 3.5 nebo WinFX, použijte starší verzi návrháře pracovních postupů.

## <a name="to-create-a-state-machine-application-project"></a>Vytvoření projektu aplikace stav počítače

1.  Spuštění sady Visual Studio.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** otevře se dialogové okno.

3.  Vyberte buď **rozhraní .NET Framework 3.0** možnost nebo **rozhraní .NET Framework 3.5** možnost v rozevíracím seznamu v horní části **nový projekt** okna pro přístup k návrháře starší verze.

    > [!NOTE]
    > Výchozí možnost v sadě Visual Studio 2010 je **rozhraní .NET Framework 4**. Tato možnost se používá k vytváření aplikací pro Windows Workflow Foundation (WF) cílených na rozhraní .NET Framework 4 a nepoužívá návrháře starší verze.

4.  V **typy projektů** podokně, vyberte Visual C# nebo Visual Basic (v části **jiné jazyky**) a potom vyberte **pracovního postupu**.

5.  V **šablony** podokně, vyberte **stavu počítače pracovního postupu konzolové aplikace**.

6.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

7.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

     Pokud chcete vytvořit pro projekt adresář řešení, vyberte **vytvořit adresář pro řešení** zaškrtněte políčko a zadejte název do pole **název řešení** pole.

8.  Click **OK**.

## <a name="see-also"></a>Viz také

- [Vytváření projektů pracovních postupů starších verzí](../workflow-designer/creating-legacy-workflow-projects.md)
- [Postupy: Vytvoření knihovny pracovních postupů stavového stroje (starší verze)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md)