---
title: "Projekty Office v prostředí Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ProjectItem.WordDocument
- VST.ProjectItem.ExcelWorkbook
- VST.ProjectItem.ExcelTemplate
- VST.ProjectItem.ExcelSheet
- VST.ProjectItem.BlueprintCode
- VST.ProjectItem.Word
- VST.ProjectItem.Excel
- VST.ProjectItem.AddinProject
- Designer_Microsoft.VisualStudio.OfficeTools.Excel.Design.WorksheetDesigner
- VST.ProjectItem.ExtendedBluePrint
- VST.ProjectItem.WordTemplate
- Designer_Microsoft.VisualStudio.OfficeTools.Word.Design.DocumentDesigner
- VST.Designer.ExcelVST.Designer.Word
- VST.ProjectItem.ExtendedBlueprintCode
- VST.ProjectItem.BluePrint
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio]
- hidden files [Office development in Visual Studio]
- project files [Office development in Visual Studio], hidden
- Office development in Visual Studio, documents in Visual Studio
- design view, Excel
- designers, Office development in Visual Studio
- Office documents [Office development in Visual Studio]
- Office documents [Office development in Visual Studio], about documents in Visual Studio
- designers [Office development in Visual Studio]
- Word designer
- Word [Office development in Visual Studio], Word designer
- Visual Studio, Office documents in
- worksheets [Office development in Visual Studio]
- VST.Designer.ExcelVST.Designer.Word
ms.assetid: 4bff36c9-4edd-4b28-89e6-0ea9f6caca02
caps.latest.revision: "58"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3f91a3ad121305e6d7a00df1ab1b337bdea73c1c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="office-projects-in-the-visual-studio-environment"></a>Projekty pro systém Office v prostředí Visual Studio
  Projekty pro Microsoft Office nabízejí vývojové prostředí, které se podobá jiným typům projektů v sadě Visual Studio, například projektům modelu Windows Forms. Při vytvoření nebo otevření projektu aplikace Office, zobrazí se položky projektu v **Průzkumníku řešení**. V případě projektů na úrovni dokumentu se dokument (tzn. dokument aplikace Word nebo sešit aplikace Excel) otevře v sadě Visual Studio a dokument se chová jako vizuální návrhář.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="project-items-in-solution-explorer"></a>Položky projektu v Průzkumníku řešení  
 V projektech na úrovni dokumentu **Průzkumníku řešení** zobrazí následující výchozí položky:  
  
-   Uzly pro dokument, sešit a listy, které jsou pomocí projektu přizpůsobeny. Tyto uzly slouží jako kontejnery pro soubory kódu, které jsou přidruženy k dokumentu, sešitu a listům.  
  
-   Soubory kódu přidružené k dokumentu, sešitu a listům, které jsou pomocí projektu přizpůsobeny. V projektech pro aplikaci Word jsou soubory kódu přidruženy k dokumentu nebo šabloně aplikace Word. V projektech pro aplikaci Excel jsou soubory kódu přidruženy k sešitu nebo šabloně aplikace Excel a ke každému listu a listu s grafem v sešitu nebo v šabloně.  
  
-   Skryté soubory projektu, které nelze přímo upravovat. Další informace najdete v tématu [zobrazení skrytých souborů projektu](#hiddenfiles).  
  
 V projektu doplňku VSTO **Průzkumníku řešení** zobrazí následující výchozí položky:  
  
-   Uzel aplikace. Tento uzel má stejný název jako hostitelskou aplikaci, například **Word**, **Excel**, nebo **Outlook**. Uzel aplikace obsahuje soubor kódu ThisAddIn. Poskytuje také **Namespace pro hostitelskou položku** vlastnost. Další informace o této vlastnosti najdete v tématu [vlastnosti v projektech Office](../vsto/properties-in-office-projects.md).  
  
-   Soubor kódu ThisAddIn. Tento soubor obsahuje vygenerovaného `ThisAddIn` třídu pro váš doplňku VSTO. Další informace o této třídy najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
-   Skryté soubory projektu, které nelze přímo upravovat. Další informace najdete v tématu [zobrazení skrytých souborů projektu](#hiddenfiles).  
  
### <a name="temporary-certificates"></a>Dočasné certifikáty  
 Projekty Office také zahrnovat dočasné certifikát s názvem *název projektu*_TemporaryKey.pfx. Tento certifikát umožňuje podepsat během vývoje projektu manifest aplikace a nasazení. Další informace najdete v tématu [udělení vztah důvěryhodnosti s řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md) a [zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md).  
  
###  <a name="hiddenfiles"></a>Soubory skrytá projektu  
 Některé soubory projektu jsou ve výchozím nastavení skryté. Tyto soubory jsou vygenerovány sadou Visual Studio a liší se podle typu projektu. Chcete-li zobrazit skryté soubory, klikněte na tlačítko **zobrazit všechny soubory** v **Průzkumníku řešení**.  
  
 Neupravujte skryté soubory projektu. Přímé změny v těchto souborech nejsou podporovány a mohou způsobit poškození projektu. Skryté soubory projektu jsou znovu vygenerovány pokaždé, když v dokumentu dojde k určitým změnám. Pokud skrytý soubor projektu ručně změníte, budou provedené změny při opětovném vygenerování souboru ztraceny.  
  
## <a name="document-designer-in-document-level-projects"></a>Návrhář dokumentu v projektech na úrovni dokumentu  
 Projekty na úrovni dokumentu pro aplikace Excel a Word poskytují návrháře, který je v sadě Visual Studio hostitelem dokumentu přidruženého k projektu. Návrhář umožňuje upravit dokument, aniž by bylo nutné opustit prostředí sady Visual Studio.  
  
 K otevření dokumentu v návrháři, poklikejte na soubor kódu v **Průzkumníku řešení** která je přiřazena k dokumentu. Například otevřete list **Sheet1** v Návrháři projektu aplikace Excel, dvakrát klikněte **Sheet1** souboru kódu.  
  
 Při úpravě dokumentu v návrháři můžete využívat nativní funkce aplikace Office. Můžete například v dokumentu nebo listu zadat text nebo pomocí pásu karet provádět operace, jako je přidání tabulky nebo grafu. Ve výchozím nastavení se používá mapování klávesových zkratek sady Visual Studio. Použití sady Office klávesové zkratky mapování místo toho změnit nastavení v části **nastavení klávesnice sady Microsoft Office** uzel v **možnosti** dialogové okno na **nástroje** nabídky .  
  
### <a name="controls-on-documents"></a>Ovládací prvky v dokumentech  
 Můžete přetáhnout *hostování ovládacích prvků* a ovládací prvky Windows Forms ze sady Visual Studio **sada nástrojů** na návrhovou plochu dokumentu. Hostitelské ovládací prvky jsou speciální verze objektů systému Office, například ovládací prvky obsahu aplikace Word nebo oblasti aplikace Excel, které lze používat v projektech pro Office vytvořených pomocí sady Visual Studio. Hostitelské ovládací prvky mají další funkce, které nejsou k dispozici v odpovídajících objektech systému Office, například datové vazby nebo další události.  
  
 Další informace najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md) a [ovládacích prvků Windows Forms na přehled dokumenty Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
### <a name="excel-worksheets-and-workbooks-in-the-designer"></a>Listy a sešity aplikace Excel v návrháři  
 Když list otevřete v návrháři, můžete jej upravovat stejně, jako byste jej otevřeli přímo v aplikaci Excel. Když dvakrát kliknete na buňku listu, přejde buňka do režimu úprav. Když dvakrát kliknete na buňku, která obsahuje hostitelský ovládací prvek, otevře se editor kódu a sada Visual Studio vygeneruje obslužnou rutinu výchozí události pro tento ovládací prvek. Pokud chcete přejít na jiné listy, můžete kliknout na ouška listů v dolní části návrháře.  
  
 Když v návrháři otevřete sešit, nezobrazí se žádná návrhová plocha. Návrhovým zobrazením sešitu je velké podokno součástí, pomocí něhož je návrhář vyplněn.  
  
 K sešitu a každému listu v sešitu je přidružen soubor kódu. Každý kód soubor obsahuje generated *hostitelská položka* třídu, která představuje sešitu nebo listu. Další informace najdete v tématu [automatizace aplikace Excel pomocí rozšířených objekty](../vsto/automating-excel-by-using-extended-objects.md).  
  
### <a name="word-documents-in-the-designer"></a>Dokumenty aplikace Word v návrháři  
 Když dokument otevřete v návrháři, můžete jej upravovat stejně, jako byste jej otevřeli přímo v aplikaci Word. Když dvakrát kliknete na slovo v dokumentu, je toto slovo vybráno. Pokud se ale toto slovo nachází uvnitř hostitelského ovládacího prvku, otevře se editor kódu a sada Visual Studio vygeneruje obslužnou rutinu výchozí události pro tento ovládací prvek.  
  
 K dokumentu je přidružen soubor kódu. Soubor kód obsahuje generated *hostitelská položka* třídu, která představuje dokumentu. Další informace najdete v tématu [hostitelská položka Document](../vsto/document-host-item.md).  
  
### <a name="design-mode-vs-run-time-mode"></a>Návrh režimu vs. Čas spuštění režimu  
 Když je dokument otevřít v prostředí Visual Studio, je vždy v *režimu návrhu*. Některé operace, například přetažení hostitelského ovládacího prvku na plochu dokumentu, lze provádět pouze v režimu návrhu.  
  
 Chcete-li zobrazit dokumentu v *režimu spuštění*, musíte otevřít aplikaci a dokumentu mimo Visual Studio. Můžete také sestavit a spustit projekt, čímž se dokument a aplikace automaticky otevřou mimo sadu Visual Studio.  
  
## <a name="code-editor"></a>Editor kódu  
 Editor kódu umožňuje prohlížet a upravovat viditelné soubory kódu ve vašem řešení. Tyto soubory obsahují kód, který definuje chování řešení.  
  
 Další informace o editoru kódu najdete v tématu [psaní kódu v editoru kódu a textovém editoru](/visualstudio/ide/writing-code-in-the-code-and-text-editor). Další informace o tom, jak napsat kód v projektech Office najdete v tématu [psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md).  
  
## <a name="properties-window"></a>Okno vlastností  
 **Vlastnosti** okně se zobrazí vlastnosti položky projektu, které jsou vybrány v **Průzkumníku**a pro prvky uživatelského rozhraní, které jsou vybrány v návrháři, jako je například ovládací prvky nebo dokumentu v projekt na úrovni dokumentu. Některé vlastnosti jsou specifické pro aplikaci a dokument a některé vlastnosti jsou stejné ve všech projektech.  
  
## <a name="data-sources-window"></a>Okno Zdroje dat  
 Můžete použít **zdroje dat** okno v projekty na úrovni dokumentu Office přetažením zdroje dat na dokument a vytvoření ovládacího prvku, který je vázán na zdroj dat. Další informace najdete v tématu [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
## <a name="see-also"></a>Viz také  
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Vlastnosti v projektech pro systém Office](../vsto/properties-in-office-projects.md)  
  
  