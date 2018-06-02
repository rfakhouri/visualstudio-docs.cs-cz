---
title: Návrhář pásu karet
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Designer_Microsoft.VisualStudio.Tools.Office.Ribbon.Design.RibbonDesigner
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, about Ribbon Designer
- controls [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], controls
- customizing the Ribbon, about Ribbon Designer
- Ribbon [Office development in Visual Studio], visual designer
- customizing the Ribbon
- custom Ribbon
- designers [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Ribbon [Office development in Visual Studio], common tasks
- Ribbon Designer [Office development in Visual Studio]
- read-only properties
- Ribbon [Office development in Visual Studio], shortcut keys
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8cb8df33c89ce044572508918ba48edae2a6d75e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34693341"
---
# <a name="ribbon-designer"></a>Návrhář pásu karet
  Návrhář pásu karet je plátno visual návrhu. Chcete-li přidat vlastní karty, skupiny a ovládacích prvků na pásu karet z aplikace Microsoft Office pomocí Návrháře pásu karet.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 Chcete-li otevřít Návrhář pásu karet, přidejte **pásu karet (vizuálního návrháře)** položku do projektu. Pak můžete použít nástroje pro návrh pro následující úkoly:  
  
-   [Návrh rozložení pásu karet](#DesigningRibbonLayout)  
  
-   [Zpracování událostí a nastavte vlastnosti ovládacích prvků](#HandleEventsSetProperties)  
  
-   [Přidání ovládacích prvků do zobrazení Backstage](#CustomizingMicrosoftOfficeButton)  
  
> [!NOTE]  
>  Existují některé úlohy, které nemůže provést pomocí Návrháře pásu karet. Další informace o těchto úlohách a jak je možné provést, najdete v části [přehled pásu karet](../vsto/ribbon-overview.md).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak I: pomocí Návrháře pásu karet k přizpůsobení pásu karet v aplikaci Outlook?](http://go.microsoft.com/fwlink/?LinkID=130312).  
  
## <a name="add-a-ribbon-visual-designer-item-to-a-project"></a>Do projektu přidat položku pásu karet (vizuálního návrháře)  
 Pokud chcete používat návrháře pásu karet, přidejte nový **pásu karet (vizuálního návrháře)** položku do projektu. Další informace najdete v tématu [postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
 Když přidáte novou **pásu karet (vizuálního návrháře)** položky, Visual Studio automaticky přidá následující soubory do projektu:  
  
-   Soubor kódu pásu karet. Tento soubor má název, který zadáte pro **pásu karet (vizuálního návrháře)** položky v **přidat novou položku** dialogové okno. Přidáte kód pro zpracování události pásu karet do tohoto souboru.  
  
-   Soubor kódu Návrhář pásu karet. Tento soubor obsahuje kód vygenerovaný Návrháře pásu karet a by neměla být upravována přímo.  
  
-   Soubor prostředků. Tento soubor obsahuje hodnoty vlastností každého ovládacího prvku na pásu karet.  
  
 Pokud již máte **pásu karet (vizuálního návrháře)** položky z jiného projektu, můžete opakovaně použít jej v aktuálním projektu pomocí **přidat existující položku** dialogové okno.  
  
##  <a name="DesigningRibbonLayout"></a> Návrh pásu karet  
 Existují tři způsoby, jak otevřít Návrhář pásu karet:  
  
-   V **Průzkumníku**, poklikejte na soubor kódu pásu karet.  
  
-   V **Průzkumníku řešení**, pravým tlačítkem na pásu karet kód soubor a pak klikněte na tlačítko **Návrhář zobrazení**.  
  
-   V **Průzkumníku řešení**, vyberte soubor kódu pásu karet a pak klikněte na tlačítko **Návrhář** na **zobrazení** nabídky.  
  
 Návrhář pásu karet obsahuje výchozí kartě a skupiny. Výchozí kartě a skupiny můžete odebrat z Návrháře pásu karet. Chcete-li odebrat do výchozí skupiny, klikněte pravým tlačítkem **Group1**a potom klikněte na **odstranit**. Pokud chcete odebrat výchozí kartě, klikněte pravým tlačítkem myši na prázdnou oblast návrhové plochy a pak klikněte na tlačítko **odebrat karta**.  
  
 Můžete také přidat vlastní karty, skupiny a ovládací prvky pro Návrháře pásu karet. Můžete najít tyto ovládací prvky v **sada nástrojů**v **ovládacích prvků pásu karet Office** skupiny. Existují tři způsoby, jak přidat ovládacích prvků z **ovládacích prvků pásu karet Office** skupiny pro Návrháře pásu karet:  
  
-   Přetáhněte ovládací prvek pro příslušnou oblast na Návrháře pásu karet.  
  
-   Klikněte na ovládací prvek a potom klikněte na příslušnou oblast v Návrháři pásu karet.  
  
-   Vyberte příslušnou oblast v návrháři a pak dvakrát klikněte na ovládací prvek v **sada nástrojů**.  
  
### <a name="ribbon-design-workflow"></a>Pracovní postup návrhu pásu karet  
 Následujícím postupem základní návrh rozložení pásu karet:  
  
1.  [Přidat vlastní karty na pásu karet](#AddTabToRibbon).  
  
2.  [Přidání skupin na kartu](#AddGroupsToTab).  
  
3.  [Přidání ovládacích prvků do skupiny](#AddControlsToGroups).  
  
 Ovládací prvky může být přetažen pouze pro skupiny; ovládací prvek nelze přetáhnout přímo na kartě a na pásu karet. Skupiny může být přetažen pouze na kartách; skupinu nelze přetáhnout přímo na pásu karet.  
  
 Uspořádání ovládacích prvků tak, že je přetáhnete na správné místo. Můžete nastavit vlastnosti ovládacího prvku pomocí **vlastnosti** okno.  
  
 Ovládací prvky nelze přetáhnout z jedné karty na jiný na pásu karet. Pokud chcete přesunout ovládacího prvku na jinou kartu, je nutné použít **Vyjmout** příkazu k odebrání ovládacího prvku z jedné karty a potom vložte ovládacího prvku na jiné kartě. Pokud vyjmutí ovládacího prvku a vložení, obslužné rutiny události přestane fungovat. Obslužné rutiny událostí v se můžete připojit **vlastnosti** okno. Další informace najdete v tématu [vlastnosti – okno](/visualstudio/ide/reference/properties-window).  
  
###  <a name="AddTabToRibbon"></a> Přidat vlastní karty na pásu karet  
 Existují tři způsoby, jak přidat vlastní karty na pásu karet:  
  
-   Přidat na kartě z **sada nástrojů**.  
  
-   Klikněte pravým tlačítkem na Návrháře pásu karet a pak klikněte na **přidat karta**.  
  
-   Otevřete **Karta Editor kolekce**a potom klikněte na **přidat**.  
  
     Otevřete **Karta Editor kolekce**v **vlastnosti** vyberte **karty** vlastnost a potom klikněte na tlačítko se třemi tečkami ![ASP.NET Mobile Návrhář elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy").  
  
 Po přidání na kartě, můžete přidat skupiny tak, aby obsahovala ovládací prvky.  
  
#### <a name="remove-custom-tabs-from-the-ribbon"></a>Odebrat vlastní karty na pásu karet  
 Existují tři způsoby, jak odebrat vlastní karty na pásu karet:  
  
-   Klikněte pravým tlačítkem designer a pak klikněte na **odebrat karta**.  
  
-   V **příkazy** podokně **vlastnosti** okně klikněte na tlačítko **odebrat karta**.  
  
-   Otevřete **Karta Editor kolekce**, vyberte kartu a pak klikněte na tlačítko **odebrat**.  
  
#### <a name="change-the-position-of-a-tab-on-the-ribbon"></a>Změna polohy karty na pásu karet  
 Můžete změnit pořadí vlastní karty na pásu karet. Můžete taky umístit vlastní karty před nebo po předdefinované karty na pásu karet. Další informace najdete v tématu [postupy: Změna polohy karty na pásu karet](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md).  
  
#### <a name="customize-built-in-tabs-on-the-ribbon"></a>Přizpůsobení předdefinované karty na pásu karet  
 Předdefinované karta je karta, která je již na pásu karet z aplikace Microsoft Office. Například **Data** karta je předdefinované karty v aplikaci Excel.  
  
 Můžete přidat skupiny a ovládací prvky pro předdefinované karty. Ve výchozím nastavení vlastních skupin se zobrazí jako poslední skupiny na předdefinované karty, i když můžete přesunout ho před nebo po žádné předdefinované skupiny na kartě.  
  
 Předdefinované skupiny nelze odebrat.  
  
 Podrobnosti o tom, jak Přizpůsobení předdefinované karty najdete v tématu [postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md).  
  
###  <a name="AddGroupsToTab"></a> Přidání skupin na kartě  
 Skupiny logicky uspořádat ovládacích prvků na pásu karet. Přidání skupin na karty. Všechny ostatní ovládací prvky přidáte do skupiny.  
  
###  <a name="AddControlsToGroups"></a> Přidání ovládacích prvků do skupiny  
 Přidejte jeden nebo více ovládacích prvků do skupiny. Následující tabulka popisuje každý ovládací prvek.  
  
|Ovládací prvek|Popis|  
|-------------|-----------------|  
|**Pole**|Kontejner, který slouží k uspořádání ovládacích prvků ve skupině. Pole s výjimkou oddělovač, skupinu nebo na kartě můžete přidat libovolný ovládací prvek. Pole může být vodorovně nebo svisle.|  
|**Tlačítko**|Tlačítko, které se spustí akce. Tlačítko můžete přidat ke skupině, skupina tlačítek, rozevíracího seznamu, galerie, nabídky nebo tlačítko rozdělení.|  
|**Skupina tlačítek**|Skupinu, která obsahuje jeden nebo více tlačítek, přepínacích tlačítek, nabídek, tlačítka rozdělení a Galerie. Skupina tlačítek můžete přidat ke skupině nebo nabídky.|  
|**CheckBox**|Pole, která zaškrtnuto nebo ne k zapnutí nebo vypnutí možnost.|  
|**ComboBox**|Textové pole se seznamem. Uživatelé můžete buď zadejte nebo vyberte si sami vyberou. V poli se zobrazí aktuální výběr. Použití <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Items%2A> vlastnost k přidání a odebrání položky v době běhu před nebo po načtení pásu karet do aplikací Office.|  
|**Rozevírací seznam**|Seznam položek, které můžete vybrat uživatele. Uživatele nelze zadat nové položky v rozevíracím seznamu.<br /><br /> Použití <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Items%2A> vlastnost k přidávání položek do seznamu. Můžete přidávat a odebírat položky v době běhu.<br /><br /> Použití <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Buttons%2A> vlastnost pro přidání tlačítek do seznamu. Nelze však přidat a odebrat tlačítka v době běhu po načtení pásu karet do aplikací Office.|  
|**Textové pole**|Pole, ve kterém může uživatel zadat text.|  
|**Galerie**|Nabídky, která uvede mřížky visual voleb, ze kterých můžete vybrat uživatele nebo pole. Můžete řídit rozložení výběr v nabídce. Použití <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> a <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> vlastnosti k určení počtu řádků a sloupců, které se zobrazí položky a tlačítka galerie.|  
|**Popisek**|Text, který můžete použít k identifikaci ovládacích prvků na pásu karet.|  
|**Nabídka**|Rozevíracího seznamu, která může obsahovat následující prvky:<br /><br /> – Tlačítko<br />-Zaškrtávací políčko<br />-Galerie<br />-Nabídky<br />– Tlačítko rozdělení<br />-Přepínací tlačítko<br />-Oddělovače<br /><br /> Přidání ovládacího prvku do nabídky v Návrháři pásu karet, klikněte na šipku dolů v nabídce vystavit povrchu návrháře nabídky. Potom můžete přetáhnout ovládacích prvků pásu karet z **sada nástrojů** na v nabídce. K uspořádání ovládacích prvků, přetáhněte je na požadované místo.<br /><br /> Přidání ovládacích prvků do <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> po pásu karet je načten do aplikace Office, je nutné nastavit <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> vlastnost **true** před načtením na pásu karet. Informace o tom, jak to udělat najdete v tématu [přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md).|  
|**Oddělovač**|Dynamické panelu slouží k oddělení položky v seznamu. Při přidání do skupiny, na panelu je svislý. Při přidání do nabídky, panelu je vodorovné.|  
|**Tlačítko rozdělení**|Tlačítko s nabídky připojit. Tlačítko rozdělení může obsahovat žádné z následujících ovládacích prvků:<br /><br /> – Tlačítko<br />-Zaškrtávací políčko<br />-Galerie<br />-Nabídky<br />– Tlačítko rozdělení<br />-Přepínací tlačítko<br />-Oddělovače<br /><br /> Stejně jako v nabídce tlačítko rozdělení má svou vlastní návrhovou plochu. Ale na rozdíl od nabídku lze aktualizovat pouze položky v tlačítko rozdělení před načtením na pásu karet do aplikací Office. Informace o aktualizaci položky v tlačítko rozdělení najdete v tématu [přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md).|  
|**ToggleButton**|Tlačítko, které se zobrazí stisknutí nebo nebyla stisknuta klávesa.|  
  
##  <a name="HandleEventsSetProperties"></a> Zpracování událostí a nastavení vlastností  
 Návrhář pásu karet umožňuje nastavit vlastnosti ovládacích prvků v době návrhu pomocí **vlastnosti** okno. Kromě toho na pásu karet zpřístupňuje model silného typu objektu, který můžete použít k získání a nastavení vlastností ovládacích prvků pásu karet za běhu.  
  
 Dvakrát klikněte na libovolný ovládací prvek v designeru otevřete obslužné rutiny události pro výchozí událost ovládacího prvku. Obslužné rutiny události pro všechny ostatní události ovládacího prvku můžete vytvořit pomocí **vlastnosti** okno.  
  
 Události pásu karet a vlastnosti, které se nacházejí v <xref:Microsoft.Office.Tools.Ribbon> oboru názvů. **Pásu karet (vizuálního návrháře)** položky automaticky přidá odkaz na toto sestavení v projektu a vloží odpovídající **pomocí** nebo **importy** příkaz nahoře k souboru kódu pásu karet.  
  
 Informace o zpracování událostí pásu karet a nastavení vlastností ovládacích prvků pásu karet za běhu najdete v tématu [přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md).  
  
##  <a name="CustomizingMicrosoftOfficeButton"></a> Přizpůsobení zobrazení Backstage  
 Návrhář pásu karet můžete použít k přidávání ovládacích prvků do nabídky, které se otevře po kliknutí **souboru** kartě. Tato nabídka je volána zobrazení Backstage.  
  
 Před nebo po integrované ovládací prvky nelze umisťování ovládacích prvků pomocí Návrháře pásu karet. Předdefinované řízení je ovládací prvek, který se již nachází v zobrazení Backstage. Pokud chcete umisťování ovládacích prvků před nebo po integrované ovládací prvky, musíte použít XML pásu karet. Další informace o **pásu karet (XML)**, najdete v části [XML karet](../vsto/ribbon-xml.md). Další informace o přizpůsobení zobrazení Backstage najdete v tématu [Úvod do zobrazení Office 2010 Backstage pro vývojáře](http://go.microsoft.com/fwlink/?LinkId=182189) a [přizpůsobit zobrazení Office 2010 Backstage pro vývojáře](http://go.microsoft.com/fwlink/?LinkId=182188).  
  
 [!INCLUDE[appliesto_ribbon_2010](../vsto/includes/appliesto-ribbon-2010-md.md)]  
  
 Informace o tom, jak přidání ovládacích prvků do zobrazení Backstage najdete v tématu [postupy: Přidání ovládacích prvků do zobrazení Backstage](../vsto/how-to-add-controls-to-the-backstage-view.md).  
  
##  <a name="Accessibility"></a> Usnadnění přístupu v Návrháři pásu karet  
 Klávesové zkratky můžete přesunout ovládací prvky v Návrháři pásu karet. Některé klávesové zkratky platí pro všechny ovládací prvky a některé platí pouze pro ovládací prvky, které mají nabídky.  
  
 Klávesové zkratky, které platí pro všechny ovládací prvky jsou uvedené v následující tabulce.  
  
|Akce|Klávesová zkratka|  
|------------|-----------------------|  
|Přesuňte ovládacího prvku před předchozí ovládacího prvku v seznamu.|**CTRL**+**nahoru**<br /><br /> **CTRL**+**doleva**|  
|Po další ovládací prvek v seznamu přesunete ovládacího prvku.|**CTRL**+**dolů**<br /><br /> **CTRL**+**vpravo**|  
|Posun výběru z jednoho ovládacího prvku do jiného ve stejné skupině. Pro rozevírací seznam panelu přesuňte mezi ovládacími prvky v panelu rozevíracího seznamu a nadřazeného ovládacího prvku.|**Nahoru**<br /><br /> **Dolů**|  
|Předat dál iterate všechny ovládací prvky.|**Karta**|  
|Opakovat a zpětného prostřednictvím všechny ovládací prvky.|**Posunutí**+**karta**|  
|Odstraňte vybraný ovládací prvek nebo sadu ovládacích prvků.|**Odstranit**|  
|Kopírování vybraných ovládacích prvků.|**CTRL**+**C**|  
|Vyjme vybrané ovládací prvky.|**CTRL**+**X**|  
|Vkládání ovládacích prvků ze schránky.|**CTRL**+**V**|  
|Vyberte **sada nástrojů**.|**CTRL**+**Alt**+**X**|  
|Vyberte komponentu nadřazené.|**ESC**|  
  
 Klávesové zkratky, které se vztahují pouze na v nabídce Microsoft Office <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>, a <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> jsou uvedeny v následující tabulce.  
  
|Akce|Klávesová zkratka|  
|------------|-----------------------|  
|Pokud otevřete panel rozevíracího seznamu a je ovládací prvek na panelu rozevíracího seznamu, vyberte nadřazeného ovládacího prvku.|**Vlevo**|  
|Zavřete panelu rozevíracího seznamu, pokud je otevřete panel rozevíracího seznamu a vybraný nadřazeného ovládacího prvku.|**Vlevo**|  
|Otevření panelu rozevíracího seznamu.|**Vpravo**|  
|První ovládací prvek v panelu rozevíracího seznamu vyberte, pokud je otevřete panel rozevíracího seznamu.|**Vpravo**|  
|Zavřete panely rozevíracího seznamu.|**ESC**|  
  
## <a name="see-also"></a>Viz také:  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Kódu XML pásu karet](../vsto/ribbon-xml.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  