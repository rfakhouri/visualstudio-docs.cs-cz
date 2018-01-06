---
title: "Usnadnění v projektech Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, accessibility
- shortcut keys [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], shortcut keys
- accessibility [Office development in Visual Studio]
ms.assetid: 48efcf1f-ca49-47ce-99f0-cc99f051aeae
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 01ef94199ae7ea22f72ca08be4dfb9092b03403f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="accessibility-in-office-projects"></a>Usnadnění v projektech pro systém Office
  Microsoft Visual Studio a Microsoft Office zahrnout mnoho funkcí usnadnění, které umožňují vytvářet vlastní řešení, které splňují požadavky na standardní usnadnění přístupu. Společnost Microsoft publikuje pokyny pro usnadnění přístupu na webu. Podrobnosti najdete v tématu [usnadnění webu](http://go.microsoft.com/fwlink/?LinkID=37113).  
  
 Ve většině případů splňovat projektech pro systém Office v sadě Visual Studio usnadnění standardy nebo zpřístupňuje vlastnosti, které můžete nastavit, aby zpřístupněte řešení. Existují však některé funkce, které mají omezenou usnadnění.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="accessibility-at-design-time"></a>Usnadnění přístupu v době návrhu  
  
### <a name="using-shortcut-keys-in-document-level-projects"></a>Použití klávesových zkratek v projekty na úrovni dokumentu  
 Pokud dokument aplikace Microsoft Office Word nebo sešitu aplikace Microsoft Office Excel je otevřen v sadě Visual Studio, obdrží pouze jednu aplikaci najednou klíče příkazy místní. Ve výchozím nastavení, Visual Studio přijme všechny příkazy klíče zástupce, ale můžete provést Word či Excel přijímat dokument má výběrem **schéma dynamické klávesnice** na **nastavení klávesnice** stránky z **možnosti** dialogové okno. Další informace najdete v tématu [Microsoft Office Word klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti](../vsto/microsoft-office-word-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md) a [Microsoft Office Excel klávesnice, nastavení klávesnice sady Microsoft Office, dialogové okno Možnosti](../vsto/microsoft-office-excel-keyboard-microsoft-office-keyboard-settings-options-dialog-box.md).  
  
### <a name="displaying-shortcut-keys-for-the-ribbon-in-document-level-projects"></a>Zobrazení zkratkových kláves pro pás karet v projektech na úrovni dokumentu  
 Pokud je v sadě Visual Studio otevřete dokument aplikace Word nebo sešitu aplikace Excel, nelze stisknutím klávesy Alt zobrazíte klávesové zkratky pro karet a ovládacích prvků na pásu karet. Chcete-li zobrazit klávesové zkratky, dokumentu nebo sešitu je otevřen v návrháři, proveďte následující kroky.  
  
##### <a name="to-view-shortcut-keys-for-ribbon-tabs-and-controls-in-the-designer"></a>Chcete-li zobrazit klávesové zkratky pro pásu karet a ovládacích prvků v Návrháři  
  
1.  V sadě Visual Studio na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  Rozbalte **Office Tools** uzel a vyberte možnost **Microsoft Office Excel klávesnice** nebo **Microsoft Office Word klávesnice**podle potřeby.  
  
3.  Vyberte **schéma dynamické klávesnice**.  
  
     Zobrazí se zpráva s oznámením, že je potřeba restartovat Visual Studio, aby změny vstoupily v platnost.  
  
4.  Click **OK**.  
  
5.  Restartujte Visual Studio a projekt znovu otevřete.  
  
6.  Otevřete dokument nebo sešitu designer pro váš projekt.  
  
7.  Stiskněte klávesu F6 zobrazíte klávesové zkratky pro pás karet.  
  
## <a name="accessibility-at-run-time"></a>Usnadnění přístupu v době běhu  
  
### <a name="windows-forms-controls-on-office-documents"></a>Windows Forms – ovládací prvky v dokumentech Office  
 Ovládací prvky Windows Forms vystavení vlastností usnadnění přístupu k poskytování informací o řízení k usnadnění, jako jsou třeba čtečky obrazovky. Pokud ovládací prvky jsou v dokumentu systému Office v přizpůsobení na úrovni dokumentu, mohou využít výhod těchto vlastností usnadnění. Další informace najdete v tématu [poskytuje informace o usnadnění pro ovládací prvky na formuláři Windows](/dotnet/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form).  
  
 V době běhu, když jsou ovládací prvky Windows Forms hostované na sešitu aplikace Excel nebo dokument aplikace Word nicméně existují určitá omezení usnadnění přístupu:  
  
-   Nelze se kartě z jednoho ovládacího prvku do jiného.  
  
-   Ovládací prvky v dokumentu jsou zakázané, když změníte nastavení přiblížení či oddálení dokumentu na jakoukoli jinou hodnotu než 100 %.  
  
 Informace o omezeních ovládacích prvků Windows Forms v dokumentech, najdete v článku [omezení z ovládacích prvků Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md).  
  
### <a name="actions-panes-and-custom-task-panes"></a>Podokna akcí a vlastních podoken úloh  
 Když podokna akce nebo vlastního podokna úloh má právě fokus, je přístup ovládací prvky stejným způsobem jako v aplikaci Windows Forms – ovládací prvky by přístup. Chcete-li přesunutím kurzoru mezi podoknem akce a dokumentu, můžete stisknout **F6**.  
  
 Další informace o podoknech akcí a vlastních podoken úloh najdete v tématu [přehled podokna akcí](../vsto/actions-pane-overview.md) a [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
### <a name="display-modes"></a>Režimy zobrazení  
 Visual Studio má následující omezení související s režimy zobrazení:  
  
-   Ovládací prvky na dokument aplikace Word nebo sešit aplikace Excel jsou zakázané, když změníte nastavení přiblížení či oddálení dokumentu na jakoukoli jinou hodnotu než 100 %.  
  
-   **Nový projekt** dialogové okno není zobrazena ovládací prvky správně, pokud uživatel změní možnosti usnadnění počítače k **použití vysoký kontrast**.  
  
 Lupa můžete překonat tato omezení. Lupa je nástroj zobrazení v systému Windows, který vytváří samostatném okně, které zobrazí oddálit část obrazovky.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Usnadnění pro postižené osoby](/visualstudio/ide/reference/accessibility-for-people-with-disabilities)   
 [Funkce sady Visual Studio pro usnadnění přístupu](/visualstudio/ide/reference/accessibility-features-of-visual-studio)  
  
  