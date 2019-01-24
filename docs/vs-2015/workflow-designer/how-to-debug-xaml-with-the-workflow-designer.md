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
ms.openlocfilehash: 053ea0c65183f57bc80b87980b100f1a76067ea8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54774929"
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Postupy: Ladění XAML pomocí návrháře postupu provádění
Pracovní postupy jsou definována v XAML. Uživatelské rozhraní reprezentace pracovního postupu je nástavbou stromu XAML definování pracovního postupu. Je podobné ladění pracovních postupů v prostředí ladění [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Například při ladění XAML, místní hodnoty, kukátko a vlákna windows fungovat stejným způsobem jako stejně jako [!INCLUDE[wfd2](../includes/wfd2-md.md)] ladění. Kromě toho zobrazení zásobníku volání během ladění XAML je založené na řádku hierarchické zobrazení toku provádění pracovního postupu.  
  
> [!NOTE]
>  Pokud XAML pro pracovní postup je umístěn ve stejném sestavení, aktivity, část sestavení pro názvy tříd nejsou zahrnuty. Bez této části názvy tříd (aktivita) nelze načíst XAML za běhu. Nedoporučuje se definovat aktivity v stejný obor názvů jako hlavní projektu. v opačném případě XAML bude potřeba ručně upravit po upravována v návrháři.  
  
### <a name="to-debug-workflow-xaml"></a>Chcete-li ladit pracovní postup XAML  
  
1.  Otevřete projekt pracovního postupu nebo aktivity v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
2.  Nastavit zarážku na aktivitu nebo aktivity, který chcete ladit, jak je popsáno v [jak: Nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md).  
  
3.  Klikněte pravým tlačítkem na soubor .xaml, který obsahuje definici pracovního postupu a vyberte **zobrazit kód**. Zobrazí se zarážku na stejném řádku jako deklarace prvku XAML, které jste nastavili zarážku na v návrhovém zobrazení aktivity.  
  
4.  Vyvolání ladicího programu, jak je popsáno v [jak: Vyvolání ladicího programu pracovních postupů](../workflow-designer/how-to-invoke-the-workflow-debugger.md).  
  
5.  Při provádění kódu dosáhnou některé z vašich zarážek, budou zvýrazněny elementu XAML přidružené k této zarážky. Chcete-li přejít k další zarážce, použijte **F10** nebo **F11** klíč.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Nastavení zarážek v pracovních postupech](../workflow-designer/how-to-set-breakpoints-in-workflows.md)   
 [Postupy: Vyvolání ladicího programu pracovních postupů](../workflow-designer/how-to-invoke-the-workflow-debugger.md)