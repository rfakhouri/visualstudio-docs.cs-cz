---
title: 'Postupy: vytváření konzolových aplikací sekvenční pracovní postup (zastaralé) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, console applications
- sequential workflows, console applications
- console applications, sequential workflow
ms.assetid: 9f7be7fa-551f-42c6-a9bb-f5ae8ab83625
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 26b479fb5f926d6dff0e1db05fe36fc4354ec89d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-sequential-workflow-console-applications-legacy"></a>Postupy: vytváření konzolových aplikací sekvenční pracovní postup (zastaralé)
Postupujte podle těchto kroků k vytvoření projektu konzolové aplikace sekvenčního pracovního postupu pomocí starší verze návrháře pracovních postupů Windows poskytované [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

### <a name="to-create-a-sequential-workflow-console-application"></a>K vytvoření konzolové aplikace sekvenční pracovní postup

1.  Spuštění sady Visual Studio.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** otevře se dialogové okno.

3.  Vyberte buď **rozhraní .NET Framework 3.0** možnost nebo **rozhraní .NET Framework 3.5** možnost v rozevíracím seznamu v horní části **nový projekt** okna pro přístup k návrháře starší verze.

    > [!NOTE]
    > Výchozí možnost v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] je **rozhraní .NET Framework 4**. Tato možnost slouží k vytvoření [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikacích, které cílí [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] a nepoužívá návrháře starší verze.

4.  V **typy projektů** podokně, vyberte projekty Visual C# nebo projekty Visual Basic (v části **jiné jazyky**) a potom vyberte **pracovního postupu**.

5.  V **šablony** podokně, vyberte **sekvenčního pracovního postupu konzolové aplikace**.

6.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

7.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

     Návrhář formulářů Windows se zobrazí Form1 projektu, který jste vytvořili.

8.  Click **OK**.

     Návrhář postupu provádění se zobrazí na plochu návrháře pracovního postupu sekvenční pracovní postup, který jste vytvořili.

9. Přetáhněte ji na aktivitu ze **sada nástrojů** na návrhovou plochu v **vyřadit aktivity** určené oblasti.

## <a name="see-also"></a>Viz také

- [Vytváření projektů pracovních postupů starších verzí](../workflow-designer/creating-legacy-workflow-projects.md)
- [Vývoj pracovních postupů](http://msdn.microsoft.com/en-us/557bcb1f-a7ab-49f6-8df7-2706b7001301)