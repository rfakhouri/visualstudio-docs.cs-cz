---
title: "Návod: Import oblasti formuláře navržené v aplikaci Outlook | Microsoft Docs"
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
- importing form regions
- form regions [Office development in Visual Studio], importing
ms.assetid: 86b0ef1a-6d7e-4ea5-b90e-458ffe4e1d10
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: cf5b5ff9f2c3b2db5d7082e4eecd9eee4e235866
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-importing-a-form-region-that-is-designed-in-outlook"></a>Návod: Import oblasti formuláře navržené v aplikaci Outlook
  Tento návod ukazuje, jak návrh oblasti formuláře v aplikaci Microsoft Office Outlook a pak import oblasti formuláře do projektu doplňku VSTO pro Outlook pomocí **nové oblasti formuláře** průvodce. Návrh oblasti formuláře v aplikaci Outlook umožňuje můžete přidat nativní ovládací prvky aplikace Outlook do oblasti formuláře, který vytvoření vazby na data Outlooku. Po importu oblasti formuláře může zpracovávat události každý ovládací prvek.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Návrh oblasti formuláře pomocí návrháře oblasti formuláře v aplikaci Outlook.  
  
-   Import oblasti formuláře do projektu doplňku VSTO v Outlooku.  
  
-   Zpracování událostí ovládacích prvků v oblasti formuláře.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)]nebo [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)].  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: vytvořit Outlook formuláře oblastí pomocí sady Visual Studio 2008?](http://go.microsoft.com/fwlink/?LinkID=130305).  
  
## <a name="designing-a-form-region-by-using-the-form-region-designer-in-outlook"></a>Návrh oblasti formuláře pomocí návrháře oblasti formuláře v aplikaci Outlook  
 V tomto kroku navrhnete oblasti formuláře v aplikaci Outlook. Budete pak uložení oblasti formuláře do umístění snadno najít tak, aby je bylo možné importovat do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
 Tento příklad oblasti formuláře zcela nahradí obvyklé úlohy formuláře. Poskytuje způsob, jak sledovat průběh všechny úlohy, které je třeba dokončit před hlavní úloha může být provedeny (požadované úkoly). Oblasti formuláře zobrazí seznam požadované úkoly a v seznamu se zobrazí stav dokončení pro každou úlohu. Uživatele můžete přidat do seznamu úloh a je odebrat. Můžete se taky aktualizovat stav dokončení každé úlohy.  
  
#### <a name="to-design-a-form-region-by-using-the-form-region-designer-in-outlook"></a>Návrh oblasti formuláře pomocí návrháře oblasti formuláře v aplikaci Outlook  
  
1.  Spusťte aplikaci Microsoft Office Outlook.  
  
2.  V aplikaci Outlook na **vývojáře** , klikněte na **návrhu formuláře**. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
3.  V **návrhu formuláře** pole, klikněte na tlačítko **úloh**a potom klikněte na **otevřete**.  
  
4.  V aplikaci Outlook na **vývojáře** ve **návrhu** klikněte na možnost **nové oblasti formuláře**.  
  
     Otevře se nové oblasti formuláře. Pokud **výběr polí** nezobrazí, klikněte na tlačítko **výběr polí** v **nástroje** skupiny.  
  
5.  Přetáhněte **subjektu** pole a **dokončeno %** pole z **výběr polí** oblasti formuláře.  
  
6.  V **nástroje** klikněte na možnost **ovládací prvky** otevřete **sada nástrojů**.  
  
7.  Přetáhněte popisek z **sada nástrojů** oblasti formuláře. Pozice popisek pod **subjektu** a **dokončeno %** pole.  
  
8.  Klikněte pravým tlačítkem na štítek a pak klikněte na **Upřesnit vlastnosti**.  
  
9. V **vlastnosti** nastavte **popisek** vlastnost **tato úloha závisí na následujících úloh**, nastavte **šířka** vlastnost **200**a potom klikněte na **použít**.  
  
10. ListBox – ovládací prvek z přetáhněte **sada nástrojů** oblasti formuláře. Pozice pole se seznamem pod **tato úloha závisí na následujících úloh** popisek.  
  
11. Vyberte seznam, který jste právě přidali.  
  
12. V **vlastnosti** nastavte **šířka** k **300**a potom klikněte na **použít**.  
  
13. Přetáhněte popisek z **sada nástrojů** oblasti formuláře. Pozice popisek pod pole se seznamem.  
  
14. Vyberte štítek, který jste právě přidali.  
  
15. V **vlastnosti** nastavte **popisek** vlastnost **, vyberte úlohu. Chcete-li přidat do seznamu závislé úlohy**, nastavte **šířka** Vlastnost **200**a potom klikněte na **použít**.  
  
16. ComboBox – ovládací prvek z přetáhněte **sada nástrojů** oblasti formuláře. Pozice pole se seznamem pod **, vyberte úlohu. Chcete-li přidat do seznamu závislé úlohy** popisek.  
  
17. Vyberte pole se seznamem, který jste právě přidali.  
  
18. V **vlastnosti** nastavte **šířka** vlastnost **300**a potom klikněte na **použít**.  
  
19. Přetáhněte ovládacího prvku CommandButton z **sada nástrojů** oblasti formuláře. Umístění příkazového tlačítka vedle pole se seznamem.  
  
20. Vyberte příkazového tlačítka, které jste právě přidali.  
  
21. V **vlastnosti** nastavte **název** k **AddDependentTask**, nastavte **popisek** k **přidat úloha závislé**, nastavte **šířka** k **100**a potom klikněte na **použít**.  
  
22. V **výběr polí**, klikněte na tlačítko **nový**.  
  
23. V **nové pole** dialogové okno, typ **hiddenField** v **název** pole a pak klikněte na **OK**.  
  
24. Přetáhněte **hiddenField** pole z **výběr polí** oblasti formuláře.  
  
25. V **vlastnosti** nastavte **viditelný** k **0 - False**a potom klikněte na **použít**.  
  
26. V aplikaci Outlook na **vývojáře** ve **návrhu** klikněte na možnost **Uložit** tlačítko a potom klikněte na **uložit oblasti formuláře jako**.  
  
     Název oblasti formuláře **TaskFormRegion** a uložte ho do místního adresáře v počítači.  
  
     Aplikace Outlook ukládá oblasti formuláře jako soubor úložiště formuláře aplikace Outlook (.ofs). Oblasti formuláře je uložen pod názvem TaskFormRegion.ofs.  
  
27. Ukončete aplikaci Outlook.  
  
## <a name="creating-a-new-outlook-add-in-project"></a>Vytvoření nové aplikace Outlook přidejte v projektu  
 V tomto kroku vytvoříte projektu doplňku VSTO v Outlooku. Dále v tomto návodu budete importovat oblasti formuláře do projektu.  
  
#### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>K vytvoření nového projektu doplňku VSTO pro Outlook  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvoření projektu doplňku VSTO pro Outlook s názvem **TaskAddIn**.  
  
2.  V **nový projekt** dialogové okno, vyberte **vytvořit adresář pro řešení**.  
  
3.  Uložte projekt do výchozí adresář projektu.  
  
     Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## <a name="importing-the-form-region"></a>Import oblasti formuláře  
 Můžete importovat oblasti formuláře navržené v aplikaci Outlook do projektu doplňku VSTO pro Outlook pomocí **nové oblasti formuláře aplikace Outlook** průvodce.  
  
#### <a name="to-import-the-form-region-into-the-outlook-vsto-add-in-project"></a>Import oblasti formuláře do projektu doplňku VSTO pro Outlook  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **TaskAddIn** projektu, přejděte na **přidat**a potom klikněte na **novou položku**.  
  
2.  V **šablony** podokně, vyberte **oblasti formuláře aplikace Outlook**, název souboru **TaskFormRegion**a potom klikněte na **přidat**.  
  
     **Oblasti formuláře NewOutlook** spustí se průvodce.  
  
3.  Na **vyberte způsob vytvoření oblasti formuláře** klikněte na tlačítko **importovat úložiště formuláře aplikace Outlook (.ofs) souboru**a potom klikněte na **Procházet**.  
  
4.  V **existující umístění souboru oblasti formuláře aplikace Outlook** dialogové okno, přejděte do umístění **TaskFormRegion.ofs**, vyberte **TaskFormRegion.ofs**, klikněte na tlačítko **Otevřete**a potom klikněte na **Další**.  
  
5.  Na **vyberte typ oblasti formuláře, které chcete vytvořit** klikněte na tlačítko **nahradit všechny**a potom klikněte na **Další**.  
  
     A *nahradit všechny* oblasti formuláře nahradí celý formuláře aplikace Outlook. Další informace o typech oblasti formuláře najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
6.  Na **zadejte popisný text a vybrat vaše předvolby zobrazení** klikněte na tlačítko **Další**.  
  
7.  Na **identifikovat zpráva třídy, které se zobrazí tato oblasti formuláře** stránky v **které třídy vlastní zpráva se zobrazí tato oblasti formuláře** zadejte **IPM. Task.TaskFormRegion**a potom klikněte na **Dokončit**.  
  
     Soubor TaskFormRegion.cs nebo TaskFormRegion.vb se přidá do projektu.  
  
## <a name="handling-the-events-of-controls-on-the-form-region"></a>Zpracování událostí ovládacích prvků v oblasti formuláře  
 Teď, když máte oblasti formuláře v projektu, můžete přidat kód, který zpracovává událost Microsoft.Office.Interop.Outlook.OlkCommandButton.Click tlačítka, které jste přidali do oblasti formuláře v aplikaci Outlook.  
  
 Navíc přidejte kód, který <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> událost, která aktualizuje ovládacích prvků na oblasti formuláře, když se zobrazí v oblasti formuláře.  
  
#### <a name="to-handle-the-events-of-controls-on-the-form-region"></a>Zpracování událostí ovládacích prvků v oblasti formuláře  
  
1.  V **Průzkumníku řešení**TaskFormRegion.cs nebo TaskFormRegion.vb klikněte pravým tlačítkem a pak klikněte na tlačítko **kód zobrazení**.  
  
     TaskFormRegion.cs nebo TaskFormRegion.vb se otevře v editoru kódu.  
  
2.  Přidejte následující kód, který `TaskFormRegion` třídy. Tento kód naplní pole se seznamem na oblasti formuláře s předmětem jednotlivých úloh ve složce aplikace Outlook úlohy.  
  
     [!code-csharp[Trin_Outlook_FR_Import#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#1)]
     [!code-vb[Trin_Outlook_FR_Import#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#1)]  
  
3.  Přidejte následující kód, který `TaskFormRegion` třídy. Tento kód provede následující:  
  
    -   Vyhledá Microsoft.Office.Interop.Outlook.TaskItem ve složce úlohy voláním `FindTaskBySubjectName` Pomocná metoda a předání předmět požadovanou úlohu. Přidáte `FindTaskBySubjectName` Pomocná metoda v dalším kroku.  
  
    -   Přidá hodnoty Microsoft.Office.Interop.Outlook.TaskItem.Subject a Microsoft.Office.Interop.Outlook.TaskItem.PercentComplete do pole se seznamem úkolů závislé.  
  
    -   Přidá předmět úlohy do pole Skrytá v oblasti formuláře. Skryté pole ukládá tyto hodnoty jako součást položky aplikace Outlook.  
  
     [!code-csharp[Trin_Outlook_FR_Import#2](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#2)]
     [!code-vb[Trin_Outlook_FR_Import#2](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#2)]  
  
4.  Přidejte následující kód, který `TaskFormRegion` třídy. Tento kód obsahuje pomocnou metodu `FindTaskBySubjectName` , je popsáno v předchozím kroku.  
  
     [!code-csharp[Trin_Outlook_FR_Import#3](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#3)]
     [!code-vb[Trin_Outlook_FR_Import#3](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#3)]  
  
5.  Přidejte následující kód, který `TaskFormRegion` třídy. Tento kód provede následující:  
  
    -   Aktualizuje pole se seznamem na oblasti formuláře s aktuálním stavem dokončení každé úlohy závislé.  
  
    -   Analyzuje pole skrytého textu, které chcete získat předmět každé závislé úlohy. Poté vyhledá každý Microsoft.Office.Interop.Outlook.TaskItem ve složce úlohy voláním `FindTaskBySubjectName` Pomocná metoda a předání předmět jednotlivých úloh.  
  
    -   Přidá hodnoty Microsoft.Office.Interop.Outlook.TaskItem.Subject a Microsoft.Office.Interop.Outlook.TaskItem.PercentComplete do pole se seznamem úkolů závislé.  
  
     [!code-csharp[Trin_Outlook_FR_Import#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#4)]
     [!code-vb[Trin_Outlook_FR_Import#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#4)]  
  
6.  Nahraďte `TaskFormRegion_FormRegionShowing` obslužné rutiny události s následujícím kódem. Tento kód provede následující:  
  
    -   Naplní pole se seznamem na oblasti formuláře s témata úkolů, když se zobrazí v oblasti formuláře.  
  
    -   Volání `RefreshTaskListBox` Pomocná metoda, jakmile se zobrazí v oblasti formuláře. Zobrazí všechny závislé úlohy, které byly přidány do seznamu, když položka byl dříve otevřen.  
  
     [!code-csharp[Trin_Outlook_FR_Import#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Import/TaskFormRegion.cs#5)]
     [!code-vb[Trin_Outlook_FR_Import#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Import_O12/TaskFormRegion.vb#5)]  
  
## <a name="testing-the-outlook-form-region"></a>Testování oblasti formuláře aplikace Outlook  
 K testování oblasti formuláře, přidání úkolů do seznamu požadovaných úloh v oblasti formuláře. Aktualizujte stav dokončení požadovaných úkolů a potom zobrazit stav aktualizované dokončení úlohy v seznamu požadovaných úloh.  
  
#### <a name="to-test-the-form-region"></a>K testování oblasti formuláře  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
     Spuštění aplikace Outlook.  
  
2.  V aplikaci Outlook na **Domů** , klikněte na **nové položky**a potom klikněte na **úloh**.  
  
3.  Ve formuláři, úloh, zadejte **závislé úlohy** v **subjektu** pole.  
  
4.  Na **úloh** karty na pásu karet v **akce** klikněte na možnost **uložit a zavřít**.  
  
5.  V aplikaci Outlook na **Domů** , klikněte na **nové položky**, klikněte na tlačítko **více položek**a potom klikněte na **zvolit formulář**.  
  
6.  V **zvolit formulář** dialogové okno, klikněte na tlačítko **TaskFormRegion**a potom klikněte na **otevřete**.  
  
     **TaskFormRegion** se zobrazí v oblasti formuláře. Tento formulář nahradí celý úkol formuláře. **, Vyberte úlohu. Chcete-li přidat do seznamu závislé úlohy** – pole se seznamem se zobrazí v dalších úloh ve složce úlohy.  
  
7.  Ve formuláři úkolu v **subjektu** zadejte **primární úloh**.  
  
8.  V **, vyberte úlohu. Chcete-li přidat do seznamu závislé úlohy** – pole se seznamem, vyberte **závislé úlohy**a potom klikněte na **přidat úloha závislé**.  
  
     **0 % Complete – závislé úlohy** se zobrazí v **tato úloha závisí na následujících úloh** pole se seznamem. Tento příklad ukazuje úspěšně zpracovat událost Microsoft.Office.Interop.Outlook.OlkCommandButton.Click tlačítka.  
  
9. Uložte a zavřete **primární úloh** položky.  
  
10. Otevřete položky závislé úlohy v aplikaci Outlook.  
  
11. Na formuláři, závislé úlohy, změňte **dokončeno %** do **50 %**.  
  
12. Na **úloh** karty závislé úlohy pásu karet v **akce** klikněte na možnost **uložit a zavřít**.  
  
13. Otevřete **primární úloh** položky aplikace Outlook.  
  
     **50 % Complete – závislé úlohy** se teď zobrazí v **tato úloha závisí na následujících úloh** pole se seznamem.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak přizpůsobit uživatelského rozhraní aplikace Outlook z těchto témat:  
  
-   Další informace o tom, jak navrhnout vzhled oblasti formuláře pomocí přetahování spravovaných ovládacích prvků do vizuálního návrháře najdete v tématu [návod: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md).  
  
-   Další informace o tom, jak přizpůsobit na pásu karet položky aplikace Outlook najdete v tématu [přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md).  
  
-   Další informace o tom, jak přidat vlastního podokna úloh do aplikace Outlook, najdete v části [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
## <a name="see-also"></a>Viz také  
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Pokyny pro vytváření oblastí formulářů aplikace Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Postupy: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Postupy: přidání oblasti formuláře do projektu doplňku aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [Vlastní akce v oblastí formulářů aplikace Outlook](../vsto/custom-actions-in-outlook-form-regions.md)   
 [Postupy: Zabránění zobrazení oblasti formuláře v aplikaci Outlook](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)  
  
  