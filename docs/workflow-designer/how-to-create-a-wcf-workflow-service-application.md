---
title: 'Postupy: vytvoření aplikace služby pracovního postupu WCF | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d901354b4a6a5f90ef75567131540405af7c9690
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>Postupy: vytvoření aplikace pracovního postupu služby WCF

[!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] aplikace služby pracovního postupu jsou distribuované komunikace služby, které předávání zpráv mezi klienty a sami přes hranice procesu. Implementace kontraktu služby na straně služby se provádí deklarativně pomocí aktivity pracovního postupu v [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] způsobem, který je obdobou starší verze služby v rozhraní .NET Framework 3.5.

### <a name="to-create-a-wcf-workflow-service-application"></a>K vytvoření aplikace pracovního postupu služby WCF

1.  Spustit [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu...** .

     **Nový projekt** otevře se dialogové okno.

3.  V **nainstalovaných šablonách** podokně, vyberte **WCF** nebo **pracovního postupu** buď z **Visual C#** nebo **jazykaVisualBasic** seskupení v závislosti na jazyk podle volby.

4.  V prostředním podokně vyberte **aplikace služby pracovního postupu WCF**.

5.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

6.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

7.  V **řešení** vyberte vytvořte nové řešení a potom klikněte na **OK**.

    > [!NOTE]
    > Pokud chcete přidat do existujícího řešení pracovního postupu konzolovou aplikaci, otevřete toto řešení v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], klikněte pravým tlačítkem na řešení v **Průzkumníku řešení**a vyberte **přidat**, pak **Nový projekt...** otevřete **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.

8.  Šablona projektu vytvoří definici služby jako XAML. Návrháři pracovních postupů Windows se otevře zobrazení návrhu s <xref:System.Activities.Statements.Sequence> aktivity, která obsahuje sadu <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity.

## <a name="see-also"></a>Viz také

- [Postupy: Vytvoření aktivity](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)