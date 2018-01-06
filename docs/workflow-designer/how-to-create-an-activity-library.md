---
title: "Postupy: vytvoření knihovna aktivit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
caps.latest.revision: "12"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: e2dc5245dd50fd2a5211d55107e537fbc8eb6eb8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-activity-library"></a>Postupy: vytvoření knihovna aktivit
Vlastní aktivity se používají pro modelování konkrétní firemních procesů v pracovním postupu. Šablona knihovny aktivit v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] bylo zadáno umožnit vytvoření takové vlastní aktivity vizuálně pomocí [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)].  
  
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
    >  Pokud chcete přidat do existujícího řešení pracovního postupu konzolovou aplikaci, otevřete toto řešení v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], klikněte pravým tlačítkem na řešení v **Průzkumníku řešení**a vyberte **přidat**, pak  **Nový projekt...**  otevřete **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.  
  
8.  Šablona projektu vytvoří definici aktivity v jazyce XAML. [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]se zobrazí na plátno vlastní aktivity.  
  
9. Přetáhněte ji na aktivitu ze **sada nástrojů** na návrhovou plochu, která chcete zahrnout do vlastní aktivity.  
  
    > [!CAUTION]
    >  Jsou povoleny pouze jednu podřízenou aktivitu v těle vlastní aktivity; však podřízené aktivity může být složené aktivity, například <xref:System.Activities.Statements.Sequence> aktivity nebo <xref:System.Activities.Statements.Flowchart> aktivity.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření aktivity](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)   
 [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)