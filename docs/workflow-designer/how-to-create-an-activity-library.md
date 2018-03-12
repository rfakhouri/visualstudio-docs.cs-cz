---
title: "Postupy: vytvoření knihovna aktivit | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 151e3f84636273de253937ebf5c91cff066b9f85
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-an-activity-library"></a>Postupy: vytvoření knihovna aktivit
Vlastní aktivity se používají pro modelování konkrétní firemních procesů v pracovním postupu. Knihovna aktivit šablony [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] bylo zadáno umožnit vytvoření takové vlastní aktivity vizuálně pomocí Návrháře pracovního postupu systému Windows.

### <a name="to-create-a-workflow-activity-library"></a>Chcete-li vytvořit knihovny aktivit pracovních postupů

1.  Spustit [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu...** .

     **Nový projekt** otevře se dialogové okno.

3.  V **typy projektů** podokně, vyberte **pracovního postupu** buď z **Visual C#** projekty nebo **jazyka Visual Basic** seskupení v závislosti na vaší jazykové předvolby.

4.  V **šablony** podokně, vyberte **knihovna aktivit**.

5.  V **název** pole, zadejte popisný název pro svůj projekt k snadno identifikovat.

6.  V **umístění** zadejte v adresáři, ve kterém chcete uložit projektu nebo klikněte na tlačítko **Procházet** přejděte k němu.

7.  V **řešení** pole, zadejte popisný název pro vaše řešení a pak klikněte na tlačítko **OK**.

    > [!NOTE]
    > Pokud chcete přidat do existujícího řešení pracovního postupu konzolovou aplikaci, otevřete toto řešení v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], klikněte pravým tlačítkem na řešení v **Průzkumníku řešení**a vyberte **přidat**, pak  **Nový projekt...**  otevřete **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.

8.  Šablona projektu vytvoří definici aktivity v jazyce XAML. Návrháři pracovních postupů Windows se zobrazí na plátno vlastní aktivity.

9. Přetáhněte ji na aktivitu ze **sada nástrojů** na návrhovou plochu, která chcete zahrnout do vlastní aktivity.

    > [!CAUTION]
    > Jsou povoleny pouze jednu podřízenou aktivitu v těle vlastní aktivity; však podřízené aktivity může být složené aktivity, například <xref:System.Activities.Statements.Sequence> aktivity nebo <xref:System.Activities.Statements.Flowchart> aktivity.

## <a name="see-also"></a>Viz také

- [Postupy: Vytvoření aktivity](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)