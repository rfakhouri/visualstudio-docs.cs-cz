---
title: 'Postupy: vytvoření knihovny aktivit pracovních postupů (zastaralé) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, activity library projects
- workflow activity libraries
- projects, workflow activity libraries
ms.assetid: fb5aa940-2ae8-4b52-b52c-51c20861a7b4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 18fa570f732f71336ce5a2f5e8e56d1185366afa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-workflow-activity-library-legacy"></a>Postupy: vytvoření knihovny aktivit pracovních postupů (zastaralé)

Postupujte podle těchto kroků k vytvoření projektu knihovny aktivit pracovních postupů pomocí starší verze návrháře pracovních postupů Windows poskytované [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

### <a name="to-create-a-workflow-activity-library-project"></a>Vytvoření projektu knihovny aktivit pracovního postupu

1.  Spuštění sady Visual Studio.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** otevře se dialogové okno.

3.  Vyberte buď **rozhraní .NET Framework 3.0** možnost nebo **rozhraní .NET Framework 3.5** možnost v rozevíracím seznamu v horní části **nový projekt** okna pro přístup k návrháře starší verze.

    > [!NOTE]
    > Výchozí možnost v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] je **rozhraní .NET Framework 4**. Tato možnost slouží k vytvoření [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikacích, které cílí [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] a nepoužívá návrháře starší verze.

4.  V **typy projektů** podokně, vyberte Visual C# nebo Visual Basic (v části **jiné jazyky**) a potom vyberte **pracovního postupu**.

5.  V **šablony** podokně, vyberte **knihovny aktivit pracovních postupů**.

6.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

7.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

     Pokud chcete vytvořit pro projekt adresář řešení, vyberte **vytvořit adresář pro řešení** zaškrtněte políčko a zadejte název do pole **název řešení** pole.

8.  Click **OK**.

## <a name="see-also"></a>Viz také

- [Vytváření projektů pracovních postupů starších verzí](../workflow-designer/creating-legacy-workflow-projects.md)
- [Používání starší verze návrháře aktivit](../workflow-designer/using-the-legacy-activity-designer.md)
- [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)
- [Vývoj aktivit pracovního postupu](http://msdn.microsoft.com/en-us/19876dfc-dfa5-4d52-b1f5-1d087474cc52)
- [Aktivity Windows Workflow Foundation](http://msdn.microsoft.com/en-us/192c4c1e-afb6-4f58-ab11-2b5bbbc2d2c0)