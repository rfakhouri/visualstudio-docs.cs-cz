---
title: "Postupy: vytváření projektů pracovního postupu (zastaralé) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflow projects, creating
- projects, workflow
ms.assetid: 32299555-662c-469d-a90d-89f4700dc78c
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: dc38c6b323ee06ed9b312811eb892e7654134d05
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-workflow-projects-legacy"></a>Postupy: vytváření projektů pracovního postupu (zastaralé)
Postupujte podle těchto kroků můžete vytvořit [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] projektu, jehož cílem [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]. Tento postup používá starší verzi návrháře pracovních postupů Windows poskytované [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

### <a name="to-create-a-workflow-project"></a>Chcete-li vytvořit projekt workflow

1.  Spustit [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)].

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** otevře se dialogové okno.

3.  Vyberte buď **rozhraní .NET Framework 3.0** možnost nebo **rozhraní .NET Framework 3.5** možnost v rozevíracím seznamu v horní části **nový projekt** okna pro přístup k návrháře starší verze.

    > [!NOTE]
    > Výchozí možnost v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] je **rozhraní .NET Framework 4**. Tato možnost slouží k vytvoření [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikacích, které cílí [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] a nepoužívá návrháře starší verze.

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