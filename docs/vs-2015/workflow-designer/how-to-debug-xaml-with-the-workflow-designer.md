---
title: 'Postupy: Ladění XAML pomocí návrháře postupu provádění | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0b8ed6bbb41b2fa3f54d825a13c16b064d010012
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444198"
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Postupy: Ladění XAML pomocí návrháře postupu provádění
Pracovní postupy jsou definována v XAML. Uživatelské rozhraní reprezentace pracovního postupu je nástavbou stromu XAML definování pracovního postupu. Je podobné ladění pracovních postupů v prostředí ladění [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Například při ladění XAML, místní hodnoty, kukátko a vlákna windows fungovat stejným způsobem jako stejně jako [!INCLUDE[wfd2](../includes/wfd2-md.md)] ladění. Kromě toho zobrazení zásobníku volání během ladění XAML je založené na řádku hierarchické zobrazení toku provádění pracovního postupu.  
  
> [!NOTE]
> Pokud XAML pro pracovní postup je umístěn ve stejném sestavení, aktivity, část sestavení pro názvy tříd nejsou zahrnuty. Bez této části názvy tříd (aktivita) nelze načíst XAML za běhu. Nedoporučuje se definovat aktivity v stejný obor názvů jako hlavní projektu. v opačném případě XAML bude potřeba ručně upravit po upravována v návrháři.  
  
### <a name="to-debug-workflow-xaml"></a>Chcete-li ladit pracovní postup XAML  
  
1. Otevřete projekt pracovního postupu nebo aktivity v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
2. Nastavit zarážku na aktivitu nebo aktivity, který chcete ladit, jak je popsáno v [jak: Nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md).  
  
3. Klikněte pravým tlačítkem na soubor .xaml, který obsahuje definici pracovního postupu a vyberte **zobrazit kód**. Zobrazí se zarážku na stejném řádku jako deklarace prvku XAML, které jste nastavili zarážku na v návrhovém zobrazení aktivity.  
  
4. Vyvolání ladicího programu, jak je popsáno v [jak: Vyvolání ladicího programu pracovních postupů](../workflow-designer/how-to-invoke-the-workflow-debugger.md).  
  
5. Při provádění kódu dosáhnou některé z vašich zarážek, budou zvýrazněny elementu XAML přidružené k této zarážky. Chcete-li přejít k další zarážce, použijte **F10** nebo **F11** klíč.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md)   
 [Postupy: Vyvolání ladicího programu pracovních postupů](../workflow-designer/how-to-invoke-the-workflow-debugger.md)