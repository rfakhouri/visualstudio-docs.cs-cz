---
title: 'Návrhář pracovního postupu: Přidat novou položku do projektu pracovního postupu'
ms.date: 06/25/2018
ms.topic: conceptual
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 29e4c03eef2a276995890bbd6b723fa457aefde2
ms.sourcegitcommit: ba5e072c9fedeff625a1332f22dcf3644d019f51
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/31/2019
ms.locfileid: "66432033"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>Postupy: Přidat novou položku do projektu pracovního postupu

Po vytvoření projektu pracovního postupu, můžete přidat do projektu aktivity pracovního postupu, návrháře a další známé položky sady Visual Studio.

V následující tabulce je přehled položek Windows Workflow Foundation (WF), které můžete přidat do projektu pracovního postupu:

| Name | Popis |
|-| - |
| Aktivita | Aktivitu se skládá z jiné aktivity. Výběrem této položky přidá stejný soubor XAML do projektu, jak lze získat při výběru **knihovny aktivit** šablonu pro nový projekt. Další informace v tomto postupu najdete v tématu [vytvořit projekt workflow](creating-a-workflow-project.md). |
| Návrhář aktivity | Návrhář pro přizpůsobení prostředí doby návrhu aktivity. Stejné soubory, které vyberete tuto položku přidá do projektu, jak lze získat při výběru **knihovny návrháře aktivit** šablonu pro nový projekt. |
| Aktivita s kódem | Aktivita s logikou provádění zapsanou v kódu. Soubor zdrojového kódu pomocí přepsání <xref:System.Activities.CodeActivity.Execute%2A> metoda byl již vygenerován za vás. |
| Služba pracovního postupu WCF | A [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] služby vytvořené pomocí aktivit pracovního postupu. Stejné soubory, které vyberete tuto položku přidá do projektu, jak lze získat při výběru **aplikace služeb pracovního postupu WCF** šablonu pro nový projekt. Další informace o tomto postupu najdete v tématu [jak: Vytvoření aplikace služeb pracovního postupu WCF](/visualstudio/workflow-designer/creating-a-workflow-project). |

## <a name="to-add-a-new-item-to-a-workflow-project"></a>Chcete-li přidat novou položku do projektu pracovního postupu

1. Na **projektu** nabídce vyberte možnost **přidat novou položku**.

   **Přidat novou položku** zobrazí se dialogové okno.

1. V levém podokně, vyberte **pracovního postupu** kategorie a pak vyberte šablonu položky pracovního postupu.

   > [!NOTE]
   > Pokud se nezobrazí **pracovního postupu** kategorie, nejdřív nainstalovali **Windows Workflow Foundation** komponentu sady Visual Studio. Podrobné pokyny najdete v tématu [nainstalovat Windows Workflow Foundation](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation).

1. Zadejte název pro položku v **název** políčko v dolní části dialogového okna.

1. Vyberte **přidat** k přidání položky do projektu.

## <a name="see-also"></a>Viz také:

- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)