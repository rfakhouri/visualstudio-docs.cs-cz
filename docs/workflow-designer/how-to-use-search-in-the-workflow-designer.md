---
title: 'Postupy: použití hledání v Návrháři pracovních postupů'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: f42d3115-2ed2-4941-8f1e-92dac41c30fa
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3e8e44586f6b0f2f8aea5ab13eb27886d7b3a6e8
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757965"
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>Postupy: použití hledání v Návrháři pracovních postupů

K usnadnění vytváření rozsáhlejších, složitějších pracovních postupů, můžete hledat v Návrháři pracovních postupů k nalezení položek podle klíčového slova. Všimněte si, že návrháře nepodporuje nahrazení.

## <a name="quick-find"></a>Rychle najít

Rychle najít vyhledá v Návrháři následující:

-   Vlastnosti <xref:System.Activities.Activity> objekty, <xref:System.Activities.Statements.FlowNode> objekty, <xref:System.Activities.Statements.State> objekty, přechody a další položky vlastní řízení toku.

-   Proměnné

-   Arguments

-   Výrazy

### <a name="use-quick-find"></a>Použití rychlého hledání

1.  Pomocí návrháře pracovních postupů otevřete, stiskněte klávesu **Ctrl + F**, nebo vyberte **upravit** > **najít a nahradit** > **rychlého hledání**.

2.  Zadejte hledaný termín do **najít** textové pole a klikněte na tlačítko **najít další**.

3.  Hledaný termín se nachází v aktuálním pracovním postupu. Následující obrázek ukazuje název zobrazení aktivity se nachází v Návrháři:

   ![Výsledek hledání v Návrháři pracovních postupů](../workflow-designer/media/designersearch.png)

## <a name="find-in-files"></a>Hledání v souborech

Najít v souborech vyhledá řetězce v soubory pracovního postupu, včetně souborů XAML.

### <a name="use-find-in-files"></a>Používání funkce najít v souborech

1.  V sadě Visual Studio, stiskněte klávesu **Ctrl**+**Shift**+**F**, nebo vyberte **upravit**  >   **Najít a nahradit** > **hledání v souborech**.

2.  Zadejte hledanou položku do **najít** textové pole a klikněte na tlačítko **najít všechny**.

3.  Výsledek hledání se zobrazí v **najít výsledek** zobrazení. Dvakrát klikněte na položku výsledek přejde na aktivitu, která obsahuje shody v Návrháři pracovních postupů.