---
title: 'Návrhář postupu provádění - postupy: vytváření projektů pracovního postupu (zastaralé)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflow projects, creating
- projects, workflow
ms.assetid: 32299555-662c-469d-a90d-89f4700dc78c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bb5d58c6d450a5e68d804e33785ec76349bfb6d8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-workflow-projects-legacy"></a>Postupy: vytváření projektů pracovního postupu (zastaralé)

Postupujte podle těchto kroků můžete vytvořit projektu Windows Workflow Foundation (WF), jehož cílem je rozhraní .NET Framework verze 3.5 nebo WinFX. Tento postup používá starší verzi návrháře pracovních postupů Windows poskytované Visual Studio 2010.

## <a name="to-create-a-workflow-project"></a>Chcete-li vytvořit projekt workflow

1.  Spuštění sady Visual Studio.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** otevře se dialogové okno.

3.  Vyberte buď **rozhraní .NET Framework 3.0** možnost nebo **rozhraní .NET Framework 3.5** možnost v rozevíracím seznamu v horní části **nový projekt** okna pro přístup k návrháře starší verze.

    > [!NOTE]
    > Výchozí možnost v sadě Visual Studio 2010 je **rozhraní .NET Framework 4**. Tato možnost se používá k vytváření aplikací pro Windows Workflow Foundation (WF) cílených na rozhraní .NET Framework 4 a nepoužívá návrháře starší verze.

4.  V **typy projektů** podokně vyberte projekty Visual C# nebo Visual Basic, projekty a pak vyberte **pracovního postupu**.

5.  V **šablony** podokně, vyberte jednu z šablony nainstalované projektu:

    -   Sekvenční pracovní postup konzolové aplikace

    -   Knihovna sekvenční pracovní postup

    -   Knihovna aktivit pracovního postupu

    -   Stav počítače pracovního postupu konzolové aplikace

    -   Knihovna stavu počítačů pracovního postupu

    -   Pracovní postup prázdný projekt

6.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

7.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte do adresáře.

     Pokud chcete vytvořit pro projekt adresář řešení, vyberte **vytvořit adresář pro řešení** zaškrtněte políčko a zadejte název do pole **název řešení** pole.

8.  Click **OK**.

## <a name="see-also"></a>Viz také

- [Vytváření projektů pracovních postupů starších verzí](../workflow-designer/creating-legacy-workflow-projects.md)