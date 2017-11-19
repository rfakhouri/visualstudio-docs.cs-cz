---
title: "Řešení potíží s chybami v řešeních pro systém Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.Project.DesignerDisabled
- VST.Designer.CannotActivate
- VST.Project.ExcelBusy
- VST.SelectDocWizard.AlreadyCustomized
- VST.SelectDocWizard.DocPath
- VST.Project.CannotOpen
- VST.Designer.ErrorsOccurred
dev_langs:
- VB
- CSharp
helpviewer_keywords: troubleshooting [Office development in Visual Studio]
ms.assetid: 8bbf5433-1992-4ecf-ae1b-19117b8ebe43
caps.latest.revision: "69"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7dd06ed6fde181760a1c4893b523bd7ef9c8dcc9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting-errors-in-office-solutions"></a>Řešení potíží s chybami v řešeních pro systém Office
  Při provádění následujících úloh při vývoji řešení pro systém Office v sadě Visual Studio se můžete setkat s problémy:  
  
-   [Vytváření, upgrade a otevírání projektů](#creating)  
  
-   [Pomocí návrháře](#designers)  
  
-   [Psaní kódu](#code)  
  
-   [Vytváření projektů](#building)  
  
-   [Ladění projektů](#debugging)  
  
##  <a name="creating"></a>Vytváření, upgrade a otevírání projektů  
 Při vytváření nebo otevírání projektů Office, může dojít k následujícím chybám.  
  
### <a name="the-project-cannot-be-created"></a>Projekt nelze vytvořit.  
 Pokud jste se pokusili vytvořit nebo otevřít projekt Office, ale Visual Studio neměl dostatek informací k určení příčinu došlo k chybě. Zkuste zavřít projekt, ukončení Visual Studio a znovu spustit.  
  
 Pokud se pokoušíte vytvořit projekt na úrovni dokumentu a, je možné, že jiného dokumentu se stejným názvem jako dokument v novém projektu je již otevřen v aplikaci Excel nebo Word. Ujistěte se, zda jsou zavřeny všechny instance aplikace Excel nebo Word.  
  
### <a name="control-properties-are-lost-when-you-create-a-new-project-based-on-a-document-from-an-existing-project"></a>Vlastnosti ovládacích prvků jsou ztráty při vytvoření nového projektu podle dokumentu z existujícího projektu  
 Pokud vytvoříte nový projekt Office podle dokumentu z existujícího projektu, vlastnosti pro všechny ovládací prvky, které jsou v dokumentu nebudou zkopírovány do nového projektu. Je nutné ručně obnovit vlastnosti pro všechny dříve existující ovládací prvky. Alternativně můžete zachovat vlastnosti ovládacích prvků tak, že vytvoříte kopii existující projekt místo vytvoření nového projektu nebo načítání existující projekt do nového řešení (v návrháři) a kopírování a vkládání ovládacích prvků z existující dokument nový dokument.  
  
### <a name="errors-when-you-create-an-excel-workbook-project-based-on-an-existing-workbook"></a>Chyby při vytváření projektu sešitu aplikace Excel podle existujícího sešitu  
 Pokud vytvoříte nový projekt sešitu aplikace Excel podle existující sešit, může se zobrazit kombinaci následující chyby.  
  
 Z aplikace Excel: "Upozornění ochrany osobních údajů: Tento dokument obsahuje makra, ovládací prvky ActiveX, informace rozšiřujícího balíku XML nebo webové komponenty. Ty mohou obsahovat osobní informace, které nelze odebrat pomocí metadat."  
  
 Ze sady Visual Studio: "Designer se nepodařilo načíst správně."  
  
 Tyto chyby může dojít, že vytvoříte projekt, který je založen na sešit, který měl jeho osobní údaje odebrat pomocí metadat. Chcete-li se vyhnout této chybě, proveďte následující kroky před vytvořením projektu.  
  
1.  Otevřete sešit v aplikaci Excel.  
  
2.  V aplikaci Excel otevřete v Centru zabezpečení.  
  
3.  Na **možnosti ochrany osobních údajů** kartě vymazat **uložení odebrat osobní informace z vlastností souboru na** zaškrtávací políčko.  
  
4.  Sešit uložte a zavřete aplikaci Excel.  
  
### <a name="cannot-open-a-project-after-migration"></a>Nelze otevřít projekt po migraci  
 Po Office, které řešení je migrovat na Microsoft Office 2010 nelze na vývojovém počítači s pouze systém Microsoft Office 2007 nainstalována otevřít projekt. Může se zobrazit následující chyby.  
  
 "Jeden nebo více projekty v řešení nebyly načíst správně. Najdete v okně výstupu podrobnosti."  
  
 "Nelze vytvořit projekt v tomto počítači není nainstalován aplikace spojené s tímto typem projektu. Je nutné nainstalovat aplikaci Microsoft Office, která souvisí s tímto typem projektu."  
  
 Chcete-li vyřešit tento problém, upravte soubor .vbproj nebo .csproj. Pro projekt aplikace Word, nahraďte HostPackage = "{763FDC83-64E5-4651-AC9B-28C4FEB985A1}" s HostPackage = "{6CE98B71-D55A-4305-87A8-0D6E368D9600}". Pro projekt aplikace Excel nahradit HostPackage = "{B284B16A-C42C-4438-BDCD-B72F4AC43CFB}" s HostPackage = "{825100CF-0BA7-47EA-A084-DCF3308DAF74}". Pro projekt aplikace Outlook nahradit HostPackage = "{D2B20FF5-A6E5-47E1-90E8-463C6860CB05}" s HostPackage = "{20A848B8-E01F-4801-962E-25DB0FF57389}".  
  
 Případně Ujistěte se, že migrované projekty jsou pouze otevřené na vývoj pro počítače s Microsoft Office 2010, která je již nainstalován.  
  
### <a name="errors-in-upgraded-office-2003-document-level-projects-that-contain-windows-forms-controls"></a>Chyby v upgradovaný projekty na úrovni dokumentu Office 2003, které obsahují ovládacích prvků Windows Forms  
 Pokud upgradujete projekt na úrovni dokumentu a Microsoft Office 2003 a dokument obsahuje ovládací prvky Windows Forms, upgradovaném projektu mohl být kompilace nebo chyby runtime. K tomuto problému vyhnout, nainstalujte sadu Visual Studio 2005 Tools for Office Runtime druhý edice na vývojovém počítači před provedením upgradu na projekt. Je k dispozici jako distribuovatelného balíčku z Microsoft Download Center v této verzi modulu runtime [Microsoft Visual Studio 2005 Tools pro druhý edice modul Runtime sady Office (VSTO 2005 SE) (x86)](http://go.microsoft.com/fwlink/?linkid=49612).  
  
 Po dokončení upgradu na projekt, můžete odinstalovat sadu Visual Studio 2005 Tools for Office Runtime druhý edici z vývojovém počítači Pokud není používán pomocí jiných řešení pro Office.  
  
##  <a name="designers"></a>Pomocí návrháře  
 Při práci s dokument, sešitu nebo listu Návrhář v projekty na úrovni dokumentu, může dojít k následujícím chybám.  
  
### <a name="designer-failed-to-load-correctly"></a>Načtení správně Designer se nezdařilo.  
 Visual Studio nelze otevřít návrháře v následujících případech:  
  
-   Aplikace Excel nebo Word již je otevřená a zobrazit modální dialogové okno. V návrháři otevřít, zkontrolujte, jestli aplikace Excel nebo Word má modální dialogové okno otevřete a zavřete všechny otevřené modálních dialogových oken. Pokud nejsou otevřeny žádné modálních dialogových oken, může být některých jiných akcí před aplikace Excel nebo Word odpoví.  
  
-   Projekt je právě laděn. Chcete-li otevřít návrháře, zastavte nebo ukončete ladění.  
  
-   Excel VSTO doplněk, který je nainstalován na vývojovém počítači je zobrazení dialogového okna, při spuštění aplikace Excel. Vytvoření projektu na úrovni dokumentu aplikace Excel, musíte nejdřív zakázat doplňku VSTO.  
  
### <a name="controls-appear-as-black-rectangles-on-the-document-or-worksheet"></a>Ovládací prvky se zobrazí jako černá obdélníky v dokumentu nebo listu  
 Pokud skupina ovládacích prvků na dokument nebo listu Visual Studio už rozpozná ovládacích prvků. Skupina ovládacích prvků nejsou přístupné v **vlastnosti** a zobrazí jako černá obdélníky v dokumentu nebo listu. Chcete-li obnovit jeho funkčnost musí oddělit ovládacích prvků.  
  
### <a name="controls-on-a-word-template-are-not-visible-in-visual-studio"></a>Ovládací prvky na šablony aplikace Word nejsou viditelné v sadě Visual Studio  
 Pokud otevřete šablonu aplikace Word v návrháři Visual Studio, nemusí být viditelné ovládací prvky v šabloně, které nejsou v textu. Je to proto, že otevře šablony aplikace Word v sadě Visual Studio **normální** zobrazení. Chcete-li zobrazit ovládací prvky, klikněte na tlačítko **zobrazení** nabídky, přejděte na příkaz **Microsoft Office Word zobrazení** a pak klikněte na **rozložením při tisku**.  
  
### <a name="insert-clip-art-command-does-nothing-in-the-visual-studio-designer"></a>Příkaz Insert klip obrázky se nic nestane. v návrháři Visual Studio  
 Pokud aplikace Excel nebo Word je otevřen v návrháři Visual Studio, kliknutím na tlačítko **Clip Art** na tlačítko **ilustrace** nelze otevřít kartu na pásu karet **Clip Art** podokna úloh. Přidat klip obrázky, otevřete kopii sešitu nebo dokument, který je ve složce hlavní projekt (nelze zkopírovat, který je ve složce \bin) mimo Visual Studio, přidejte jej do galerie a potom uložte sešit nebo dokumentu.  
  
##  <a name="code"></a>Psaní kódu  
 Při psaní kódu v projektech Office, může dojít k následujícím chybám.  
  
### <a name="some-events-of-office-objects-are-not-accessible-when-using-c"></a>Některé události objektů Office nejsou dostupné, když pomocí jazyka C#  
 V některých případech se může zobrazit chyba kompilátoru takto při pokusu o přístup k určité události instance Office primární spolupracující sestavení (PIA) zadejte v projektu jazyka Visual C#.  
  
 "Nejednoznačnost mezi 'Microsoft.Office.Interop.Excel._Application.NewWorkbook' a 'Microsoft.Office.Interop.Excel.AppEvents_Event.NewWorkbook."  
  
 Tato chyba znamená, že se pokoušíte získat přístup na událost, která má stejný název jako jiný vlastnost nebo metodu objektu. Pro přístup k události, musíte převést objekt, který má jeho *rozhraní události*.  
  
 Typy PIA – Office, které mají události implementovat dvě rozhraní: základní rozhraní se všechny vlastnosti a metody a události rozhraní, které obsahuje události, které jsou vystavené objektu. Tyto události rozhraní použít zásady vytváření názvů *objectname*události*n*_událost, jako například <xref:Microsoft.Office.Interop.Excel.AppEvents_Event> a <xref:Microsoft.Office.Interop.Word.ApplicationEvents2_Event>. Pokud nemůžete použít událost, který chcete nalézt v objektu, přetypujte objekt, který má jeho událostí rozhraní.  
  
 Například <xref:Microsoft.Office.Interop.Excel.Application> objekty mají <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.NewWorkbook> událostí a <xref:Microsoft.Office.Interop.Excel._Application.NewWorkbook%2A> vlastnost. Zpracování <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.NewWorkbook> přetypovat <xref:Microsoft.Office.Interop.Excel.Application> k <xref:Microsoft.Office.Interop.Excel.AppEvents_Event> rozhraní. Následující příklad kódu ukazuje, jak to udělat v projektech na úrovni dokumentu pro Excel.  
  
 [!code-csharp[Trin_VstcoreTroubleshootingExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreTroubleshootingExcelCS/ThisWorkbook.cs#1)]  
  
 Další informace o události rozhraní PIA Office, najdete v části [přehled třídy a rozhraní v primární zprostředkovatel komunikace s objekty sestavení sady Office](http://msdn.microsoft.com/en-us/da92dc3c-8209-44de-8095-a843659368d5).  
  
### <a name="cannot-reference-office-pia-classes-in-projects-that-target-the-includenetv40shortsharepointincludesnet-v40-short-mdmd-or-the-includenetv45vstoincludesnet-v45-mdmd"></a>Neodkazují na Office PIA – třídy v projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], nebude ve výchozím nastavení kompilace kódu, který odkazuje na třídu, která je definována v PIA – Office. Použít zásady vytváření názvů tříd v PIA *objectname*třídy, jako například <xref:Microsoft.Office.Interop.Word.DocumentClass> a <xref:Microsoft.Office.Interop.Excel.WorkbookClass>. Například nebude Zkompilujte následující kód z projektu doplňku VSTO pro Word.  
  
```vb  
Dim document As Word.DocumentClass = Globals.ThisAddIn.Application.ActiveDocument  
```  
  
```csharp  
Word.DocumentClass document = (Word.DocumentClass) Globals.ThisAddIn.Application.ActiveDocument;  
```  
  
 Tento kód vrátí následující chyby kompilace:  
  
-   Visual Basic: "odkazu na třídu 'Třídu DocumentClass' není povolena při jeho sestavení je propojení pomocí režimu No-PIA."  
  
-   Visual C#: "zprostředkovatele komunikace s objekty typu 'Microsoft.Office.Interop.Word.DocumentClass' nelze vložit. Použijte příslušné rozhraní."  
  
 Chcete-li tuto chybu vyřešit, upravte kód tak, aby odkazovaly na odpovídající rozhraní místo. Například místo odkazu <xref:Microsoft.Office.Interop.Word.DocumentClass> objektu, odkazovat na instanci <xref:Microsoft.Office.Interop.Word.Document> místo toho rozhraní.  
  
```vb  
Dim document As Word.Document = Globals.ThisAddIn.Application.ActiveDocument  
```  
  
```csharp  
Word.Document document = Globals.ThisAddIn.Application.ActiveDocument;  
```  
  
 Projektů cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], automaticky vložené všechny typy spolupráce z PIA Office ve výchozím nastavení. K této chybě kompilace dojde, protože funkce vestavěné typy spolupráce funguje pouze s rozhraními, nikoli třídy. Další informace o rozhraní a třídy v Office PIA najdete v tématu [přehled třídy a rozhraní v primární zprostředkovatel komunikace s objekty sestavení sady Office](http://go.microsoft.com/fwlink/?LinkId=189592). Další informace o funkci vestavěné typy spolupráce v projektech Office najdete v tématu [návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="references-to-office-classes-are-not-recognized"></a>Odkazy na třídy Office nebyl rozpoznán.  
 Některé názvy tříd, například aplikace, jsou ve více obory názvů, jako <xref:Microsoft.Office.Interop.Word> a <xref:System.Windows.Forms>. Z tohoto důvodu **importy**/**pomocí** zahrnuje příkaz v horní části šablony projektů sdruženou kvalifikující konstanta, například:  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreTroubleshootingWordCS/ThisDocument.cs#2)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreTroubleshootingWordVB/ThisDocument.vb#2)]  
  
 Toto použití **importy**/**pomocí** příkaz vyžaduje rozlišit odkazy na třídy Office s Word či Excel kvalifikátor, například:  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#3](../vsto/codesnippet/CSharp/Trin_VstcoreTroubleshootingWordCS/ThisDocument.cs#3)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreTroubleshootingWordVB/ThisDocument.vb#3)]  
  
 Pokud například používáte nekvalifikované deklarace, bude docházet k chybám:  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#4](../vsto/codesnippet/CSharp/Trin_VstcoreTroubleshootingWordCS/ThisDocument.cs#4)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreTroubleshootingWordVB/ThisDocument.vb#4)]  
  
 I když jste importovali Word či Excel obor názvů a získat přístup k všechny třídy je uvnitř, musí k plnému určení všech typů s Word či Excel k odebrání oboru názvů nejednoznačnosti.  
  
##  <a name="building"></a>Vytváření projektů  
 Při sestavování projektů Office, může dojít k následujícím chybám.  
  
### <a name="cannot-build-a-document-level-project-that-is-based-on-a-document-with-restricted-permissions"></a>Nelze vytvořit projekt na úrovni dokumentu, který je založen na dokument s omezenými oprávněními  
 Visual Studio nemůže vytvořit projekty na úrovni dokumentu, pokud dokument má omezená oprávnění. Pokud projekt obsahuje dokument, který má omezená oprávnění, nebude kompilace projektu a zobrazí se následující zpráva v **seznam chyb** okno.  
  
 "Nepodařilo se přidat přizpůsobení."  
  
 Pokud chcete zahrnout dokument, který má omezená oprávnění, neomezený dokument použijte, když jste sami vyvinuli a sestavte řešení. Přiřaďte omezená oprávnění k dokumentu v umístění pro publikování, po publikování řešení.  
  
### <a name="compiler-errors-occur-after-a-namedrange-control-is-deleted"></a>Po odstranění ovládacího prvku NamedRange dojít k chybám kompilátoru  
 Pokud odstraníte <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení z listu, která není v aktivním listu v Návrháři automaticky vygenerovaný kód nemusí odeberou z projektu a může dojít k chybám kompilátoru. Pokud chcete mít jistotu, kód se odebere, byste měli vždy vybrat listu, který obsahuje <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek, aby bylo před odstraněním ovládací prvek aktivního listu. Pokud automaticky vygenerovaný kód není odstraněna při odstranění ovládacího prvku, může způsobit návrháře odstranit kód tak, že aktivace listu a změnu tak, aby listu bude označena jako upravená. Pokud projekt znovu sestavte, odebere se kód.  
  
##  <a name="debugging"></a>Ladění projektů  
 Při ladění projektů Office, může dojít k následujícím chybám.  
  
### <a name="prompt-to-uninstall-appears-when-you-publish-and-install-a-solution-on-the-development-computer"></a>Výzva k odinstalaci se zobrazí, když je publikování a nainstalovat řešení na vývojovém počítači  
 Při ladění řešení Office, může se zobrazit následující chyby.  
  
 "Přizpůsobení nelze nainstalovat, protože je aktuálně nainstalována jiná verze a z tohoto umístění nelze upgradovat."  
  
 Tato chyba znamená, že jste publikována a nainstalované řešení Office na vývojovém počítači. Chcete-li zabránit zobrazování zprávy, odinstalujte řešení ze seznamu nainstalovaných programů v počítači před ladění řešení. Případně můžete vytvořit jiného uživatelského účtu ve svém vývojovém počítači k testování instalace publikované řešení.  
  
### <a name="document-level-projects-created-at-unc-network-locations-do-not-run-from-visual-studio"></a>Projekty na úrovni dokumentu vytvořený v umístění v síti UNC se nespustí ze sady Visual Studio  
 Pokud vytvoříte projekt na úrovni dokumentu pro Excel nebo Word na síťové umístění UNC, musíte přidat do seznamu důvěryhodných umístění v aplikaci Excel nebo Word umístění dokumentu. Přizpůsobení, jinak nebudou načteny, při pokusu o spuštění nebo ladění projektu v sadě Visual Studio. Další informace o důvěryhodných umístění najdete v tématu [udělení vztah důvěryhodnosti s dokumenty](../vsto/granting-trust-to-documents.md).  
  
### <a name="threads-are-not-stopped-correctly-after-debugging"></a>Vlákna není správně zastavena po ladění  
 Projekty Office v sadě Visual Studio podle vlákno konvence, která umožňuje ladicího programu zavřete program správně. Pokud vytvoříte vláken ve vašem řešení, má název každé vlákno s předponou VSTA_ zajistit, že tyto vláken jsou zpracovávány jako správně, když zastavíte ladění. Například může nastavit `Name` vlastnost vlákno, které čeká událost sítě **VSTA_NetworkListener**.  
  
### <a name="cannot-run-or-debug-any-office-solution-on-the-development-computer"></a>Nelze spustit nebo ladění řešení Office na vývojovém počítači  
 Pokud nelze spustit, nebo vyvíjet Microsoft Office project ve svém vývojovém počítači, zobrazí se následující chybová zpráva.  
  
 "Přizpůsobení nelze načíst, protože nelze vytvořit doménu aplikace."  
  
 Visual Studio použije Fusion, zavaděč sestavení rozhraní .NET Framework a pro ukládání do mezipaměti sestavení před načtením řešení pro systém Office. Zajistěte, aby Visual Studio můžete zapsat do mezipaměti Fusion a zkuste to znovu. Další informace najdete v tématu [stínové kopírování sestavení](/dotnet/framework/app-domains/shadow-copy-assemblies).  
  
### <a name="error-when-stopping-the-debugger-in-a-document-level-project-after-using-edit-and-continue"></a>Chyba při zastavení ladicího programu v projektech na úrovni dokumentu po použití operace upravit a pokračovat  
 Používáte-li provést změny kódu v projektech na úrovni dokumentu pro Excel nebo Word při projekt je v režimu pozastavení upravit a pokračovat, může zobrazit dialogové okno se následující chybová zpráva, pokud následně zastavení ladicího programu.  
  
 "Proces v jejím aktuálním stavu se ukončuje může způsobit nežádoucí výsledky včetně ztrátu dat a nestability systému."  
  
 Jestli kliknutí **Ano** nebo **ne** v dialogovém okně Visual Studio ukončí proces aplikace Excel nebo Word a zastaví ladicího programu. Chcete-li ukončete ladění projektu bez zobrazení tohoto dialogového okna, ukončete aplikaci Excel nebo Word přímo místo zastavení ladicího programu v sadě Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Řešení potíží s řešení pro systém Office](../vsto/troubleshooting-office-solutions.md)   
 [Řešení potíží se zabezpečením řešení Office](../vsto/troubleshooting-office-solution-security.md)   
 [Řešení potíží s nasazením řešení Office](../vsto/troubleshooting-office-solution-deployment.md)  
  
  