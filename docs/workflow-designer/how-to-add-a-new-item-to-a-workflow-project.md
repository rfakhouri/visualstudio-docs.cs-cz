---
title: 'Návrhář postupu provádění - postupy: Přidání nové položky do projektu pracovního postupu'
ms.date: 06/25/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3f1202c87986eab6af899a3d4c3b7a5f62e5af6
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757676"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Postupy: Přidání nové položky do projektu pracovního postupu

Po vytvoření projektu workflow, můžete přidat do projektu aktivity pracovního postupu, Designer a další známé položky Visual Studio.

Následující tabulka uvádí položky Windows Workflow Foundation (WF), které můžete přidat do projektu pracovního postupu:

|Název|Popis|
|----------|-----------------|
|Aktivita|Aktivity k musí se skládat z jiné aktivity. Výběrem této položky přidá ke stejnému souboru XAML do projektu, jak lze získat při výběru **knihovna aktivit** šablonu pro nový projekt. Další informace o na tomto postupu najdete v tématu [postupy: vytvoření knihovna aktivit](../workflow-designer/how-to-create-an-activity-library.md).|
|Návrhář aktivity|Návrhář přizpůsobit prostředí návrhu aktivity. Stejné soubory, které výběrem této položky přidáte do projektu, jak lze získat při výběru **knihovny návrháře aktivit** šablonu pro nový projekt. Další informace o na tomto postupu najdete v tématu [postupy: vytvoření knihovny návrháře aktivit](../workflow-designer/how-to-create-an-activity-designer-library.md).|
|Kód aktivity|Aktivita, jejíž logiky provádění napsané v kódu. Soubor zdrojového kódu se pomocí přepsání <xref:System.Activities.CodeActivity.Execute%2A> metoda byl již vygenerován za vás.|
|Pracovní postup služby WCF|A [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] služby vytvořené pomocí aktivity pracovního postupu. Stejné soubory, které výběrem této položky přidáte do projektu, jak lze získat při výběru **aplikace služby pracovního postupu WCF** šablonu pro nový projekt. Další informace o tomto postupu najdete v tématu [postupy: vytvoření aplikace služby pracovního postupu WCF](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md).|

## <a name="to-add-a-new-item-to-a-workflow-project"></a>Chcete-li přidat novou položku do projektu pracovního postupu

1. Na **projektu** nabídce vyberte možnost **přidat novou položku**.

   **Přidat novou položku** otevře se dialogové okno.

1. V levém podokně, vyberte **pracovního postupu** kategorie a potom vyberte šablonu položky pracovního postupu.

   > [!NOTE]
   > Pokud nevidíte **pracovního postupu** kategorie, první instalaci **modelu Windows Workflow Foundation** součást produktu Visual Studio 2017. Podrobné pokyny najdete v tématu [nainstalovat Windows Workflow Foundation](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation).

1. Zadejte název položky v **název** pole v dolní části dialogových oken.

1. Vyberte **přidat** přidat položku do projektu.

## <a name="see-also"></a>Viz také:

- [Vytvořit projekt workflow](../workflow-designer/creating-a-workflow-project.md)