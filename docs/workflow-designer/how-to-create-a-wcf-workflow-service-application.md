---
title: 'Návrhář postupu provádění - postupy: vytvoření aplikace pracovního postupu služby WCF'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93fb69862c228a3b6e61467facba188dd20c67c7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>Postupy: vytvoření aplikace pracovního postupu služby WCF

Aplikace služby Windows Communication Foundation (WCF) pracovního postupu jsou distribuované komunikace služby, které předávání zpráv mezi klienty a sami přes hranice procesu. Implementace kontraktu služby na straně služby se provádí deklarativně pomocí aktivity pracovního postupu v rozhraní .NET Framework 4 způsobem, který je obdobou starší verze služby v rozhraní .NET Framework 3.5.

## <a name="to-create-a-wcf-workflow-service-application"></a>K vytvoření aplikace pracovního postupu služby WCF

1.  Spusťte sadu Visual Studio 2010.

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** otevře se dialogové okno.

3.  V **nainstalovaných šablonách** podokně, vyberte **WCF** nebo **pracovního postupu** buď z **Visual C#** nebo **jazykaVisualBasic** seskupení v závislosti na jazyk podle volby.

4.  V prostředním podokně vyberte **aplikace služby pracovního postupu WCF**.

5.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

6.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

7.  V **řešení** vyberte vytvořte nové řešení a potom klikněte na **OK**.

    > [!NOTE]
    > Pokud chcete přidat do existujícího řešení pracovního postupu konzolovou aplikaci, otevřete toto řešení v sadě Visual Studio 2010, klikněte pravým tlačítkem na řešení v **Průzkumníku řešení**a vyberte **přidat**, pak  **Nový projekt** otevřete **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.

8.  Šablona projektu vytvoří definici služby jako XAML. Návrháři pracovních postupů Windows se otevře zobrazení návrhu s <xref:System.Activities.Statements.Sequence> aktivity, která obsahuje sadu <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity.

## <a name="see-also"></a>Viz také

- [Postupy: Vytvoření aktivity](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)