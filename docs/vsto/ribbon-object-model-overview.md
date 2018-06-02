---
title: Přehled modelu objektů pásu karet
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], object model
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2be8f0ecdb4f2d7a8ea379474c4b5ec0062d2b57
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692958"
---
# <a name="ribbon-object-model-overview"></a>Přehled modelu objektů pásu karet
  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Zpřístupňuje model silného typu objektu, který můžete použít k získání a nastavení vlastností ovládacích prvků pásu karet za běhu. Například můžete dynamicky naplnit ovládací prvky nabídky, nebo zobrazení a skrytí ovládacích prvcích kontextově. Na pásu karet, ale jenom dříve, než na pásu karet je načtena podle aplikace Office, můžete přidat také karty, skupiny a ovládací prvky. Informace najdete v tématu [nastavte vlastnosti, které jen pro čtení](#SettingReadOnlyProperties).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 Tento objektový model pásu karet tvořená především [pásu karet třída](#RibbonClass), [pásu karet události](#RibbonEvents), a [– třídy ovládacích prvků pásu karet](#RibbonControlClasses).  
  
##  <a name="RibbonClass"></a> Pás karet – třída  
 Když přidáte novou **pásu karet (vizuálního návrháře)** položku do projektu, přidá aplikace Visual Studio **pásu karet** třídu do projektu. **Pásu karet** třída dědí z <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> třídy.  
  
 Tato třída se zobrazí jako částečný třídu, která je rozdělená mezi souboru kódu pásu karet a souboru kódu Návrhář pásu karet.  
  
##  <a name="RibbonEvents"></a> Události pásu karet  
 **Pásu karet** třída obsahuje následující tři události:  
  
|Událost|Popis|  
|-----------|-----------------|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Load>|Vyvolá, když aplikace Office načte přizpůsobení pásu karet. <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load> Obslužné rutiny události se automaticky přidá do souboru kódu pásu karet. Pomocí této obslužné rutiny události při načtení pásu karet spusťte vlastní kód.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.LoadImage>|Umožňuje mezipaměti obrázků v přizpůsobení pásu karet při načtení pásu karet. Můžete získat mírné výkonnější, pokud napsat kód pro ukládání do mezipaměti obrázků pásu karet v této obslužné rutiny události. Další informace naleznete v tématu <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Close>|Vyvolána při zavření instance pásu karet.|  
  
##  <a name="RibbonControlClasses"></a> Ovládací prvky pásu karet  
 <xref:Microsoft.Office.Tools.Ribbon> Obor názvů obsahuje typ pro každý ovládací prvek, který se zobrazí v **ovládacích prvků pásu karet Office** u **sada nástrojů**.  
  
 Následující tabulka uvádí pro každý typ `Ribbon` ovládacího prvku. Popis každého ovládacího prvku naleznete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
|Název ovládacího prvku|Název třídy|  
|------------------|----------------|  
|**Pole**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|  
|**Tlačítko**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|  
|**Skupina tlačítek**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|  
|**CheckBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|  
|**ComboBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|  
|**Rozevírací seznam**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>|  
|**Textové pole**|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**Galerie**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**Skupiny**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|  
|**Popisek**|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|  
|**Nabídka**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|  
|**Oddělovač**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|  
|**Tlačítko rozdělení**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**Karta**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**ToggleButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
  
 <xref:Microsoft.Office.Tools.Ribbon> Obor názvů používá předpona "Pásu karet" pro tyto typy aby nedošlo ke kolizi názvu s názvy – třídy ovládacích prvků v <xref:System.Windows.Forms> oboru názvů.  
  
 Při přidání ovládacího prvku do Návrháře pásu karet, Návrhář pásu karet deklaruje třídu pro ovládací prvek v poli v souboru kódu Návrhář pásu karet.  
  
### <a name="common-tasks-using-the-properties-of-ribbon-controls"></a>Běžné úlohy pomocí vlastností ovládacích prvků pásu karet  
 Každý `Ribbon` ovládací prvek obsahuje vlastnosti, které můžete provádět různé úlohy, jako je například přiřazení do ovládacího prvku popisek nebo skrytí a zobrazení ovládacích prvků.  
  
 V některých případech stát vlastnosti jen pro čtení po zatížení pásu karet nebo po přidání ovládacího prvku do dynamické nabídky. Další informace najdete v tématu [nastavte vlastnosti, které jen pro čtení](#SettingReadOnlyProperties).  
  
 Následující tabulka popisuje některé z úloh, které můžete provádět pomocí `Ribbon` vlastností ovládacího prvku.  
  
|K této úloze:|postupujte takto:|  
|--------------------|--------------|  
|Skrytí nebo zobrazení ovládacího prvku.|Použijte vlastnost Visible.|  
|Povolit nebo zakázat ovládacího prvku.|Použijte vlastnost povoleno.|  
|Nastavení velikosti ovládacího prvku.|Použijte vlastnost ControlSize.|  
|Získáte bitovou kopii, která se zobrazí v ovládacím prvku.|Použijte vlastnost bitové kopie.|  
|Změna štítku ovládacího prvku.|Použijte vlastnost popisku.|  
|Přidáte uživatelská data do ovládacího prvku.|Použijte vlastnost značky.|  
|Získání položky v <xref:Microsoft.Office.Tools.Ribbon.RibbonBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>, nebo<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> ovládací prvek.|Pomocí vlastnosti položky.|  
|Přidat položky do <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, nebo <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> ovládacího prvku.|Pomocí vlastnosti položky.|  
|Přidání ovládacích prvků k <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>.|Pomocí vlastnosti položky.<br /><br /> Přidání ovládacích prvků do <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> po pásu karet je načten do aplikace Office, je nutné nastavit <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> vlastnost **true** před načtením na pásu karet do aplikace Office. Informace najdete v tématu [nastavte vlastnosti, které jen pro čtení](#SettingReadOnlyProperties).|  
|Získat vybrané položce <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>,<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, nebo <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>.|Použijte vlastnost SelectedItem. Pro <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>, použijte <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Text%2A> vlastnost.|  
|Získat skupiny <xref:Microsoft.Office.Tools.Ribbon.RibbonTab>.|Použití <xref:Microsoft.Office.Tools.Ribbon.RibbonTab.Groups%2A> vlastnost.|  
|Zadejte počet řádků a sloupců, které se zobrazují v <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>.|Použití <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> a <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> vlastnosti.|  
  
##  <a name="SettingReadOnlyProperties"></a> Nastavte vlastnosti, které jen pro čtení  
 Některé vlastnosti lze nastavit pouze před načte pásu karet. Existují tři místa a nastavte tyto vlastnosti:  
  
-   V sadě Visual Studio **vlastnosti** okno.  
  
-   V konstruktoru **pásu karet** třídy.  
  
-   V `CreateRibbonExtensibilityObject` metodu `ThisAddin`, `ThisWorkbook`, nebo `ThisDocument` třídu do projektu.  
  
 Dynamické nabídky poskytují některé výjimky. Můžete vytvořit nové ovládací prvky, nastavit jejich vlastnosti a pak je přidejte do dynamická nabídka za běhu, i když je načten na pásu karet, která obsahuje v nabídce.  
  
 Kdykoli můžete nastavit vlastnosti pro ovládací prvky, které přidáte do dynamické nabídky.  
  
 Další informace najdete v tématu [vlastnosti, které jen pro čtení](#ReadOnlyProperties).  
  
### <a name="set-properties-in-the-constructor-of-the-ribbon"></a>Nastavit vlastnosti v konstruktoru pásu karet  
 Můžete nastavit vlastnosti `Ribbon` ovládací prvek v konstruktoru **pásu karet** třídy. Tento kód musí být po volání `InitializeComponent` metoda. Následující příklad přidá nové tlačítko pro skupinu, pokud je aktuální čas 17:00 tichomořského času (UTC-8) nebo novější.  
  
 Přidejte následující kód.  
  
 [!code-csharp[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.cs#1)]
 [!code-vb[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.vb#1)]  
  
 V jazyce Visual C# projekty, které jste upgradovali ze sady Visual Studio 2008 konstruktoru se zobrazí v souboru kódu pásu karet.  
  
 V projektech Visual Basic nebo v projektech Visual C#, které jste vytvořili v [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], konstruktoru se zobrazí v souboru kódu Návrhář pásu karet. Název tohoto souboru je *YourRibbonItem*. Designer.cs nebo *YourRibbonItem*. Designer.vb. Pokud chcete zobrazit tento soubor v projektech Visual Basic, musíte nejprve klikněte **zobrazit všechny soubory** tlačítko v Průzkumníku řešení.  
  
### <a name="set-properties-in-the-createribbonextensibilityobject-method"></a>Nastavit vlastnosti v metodě CreateRibbonExtensibilityObject  
 Můžete nastavit vlastnosti `Ribbon` řízení při přepsání `CreateRibbonExtensibilityObject` metoda v `ThisAddin`, `ThisWorkbook`, nebo `ThisDocument` třídu do projektu. Další informace o `CreateRibbonExtensibilityObject` metodu, najdete v části [přehled pásu karet](../vsto/ribbon-overview.md).  
  
 Následující příklad nastavuje vlastnosti pásu karet v `CreateRibbonExtensibilityObject` metodu `ThisWorkbook` třída projektu sešitu aplikace Excel.  
  
 Přidejte následující kód.  
  
 [!code-vb[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.vb#2)]
 [!code-csharp[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.cs#2)]  
  
###  <a name="ReadOnlyProperties"></a> Vlastnosti, které jen pro čtení  
 V následující tabulce jsou uvedeny vlastnosti, které lze nastavit pouze před načte pásu karet.  
  
> [!NOTE]  
>  Kdykoli můžete nastavit vlastnosti ovládacích prvků na dynamické nabídky. Tato tabulka v takovém případě neplatí.  
  
|Vlastnost|Třída ovládacích prvků pásu karet|  
|--------------|--------------------------|  
|**BoxStyle**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|  
|**ButtonType**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**Počet sloupců**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ControlId**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**DialogLauncher**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|  
|**dynamické**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|  
|**Globální**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**Skupiny**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**ImageName**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
|**ItemSize**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**Hodnota maxLength**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**Jméno**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComponent>|  
|**Pozice**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonTab><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
|**RibbonType**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**Atribut RowCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemImage**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemLabel**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemSelection**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**SizeString**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**StartFromScratch**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**Karty**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**Název**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|  
  
### <a name="set-properties-for-ribbons-that-appear-in-outlook-inspectors"></a>Nastavit vlastnosti pro pásů karet, které se zobrazují v aplikaci Outlook kontroly  
 Pokaždé, když uživatel otevře Inspector, ve kterém se zobrazí na pásu karet se vytvoří novou instanci třídy na pásu karet. Však můžete nastavit vlastnosti uvedené v předchozí tabulce pouze před vytvořením první instance na pásu karet. Po první instance je vytvořen, tyto vlastnosti stát jen pro čtení, protože první instance definuje souboru XML, který používá aplikace Outlook k načtení pásu karet.  
  
 Pokud máte podmíněnou logiku, která nastavuje kterékoli z těchto vlastností na jinou hodnotu, při vytváření ostatní instance na pásu karet, tento kód nebude mít žádný vliv.  
  
> [!NOTE]  
>  Ujistěte se, že **název** je nastavena pro každý ovládací prvek, která přidáte do pásu karet aplikace Outlook. Pokud přidáte ovládacího prvku do aplikace Outlook pásu karet za běhu, musíte tuto vlastnost nastavit v kódu. Přidání ovládacího prvku na pásu karet aplikaci Outlook v době návrhu, je vlastnost názvu nastavena automaticky.  
  
## <a name="ribbon-control-events"></a>Události ovládacích prvků pásu karet  
 Každá třída ovládací prvek obsahuje jeden nebo více událostí. Následující tabulka popisuje tyto události.  
  
|Událost|Popis|  
|-----------|-----------------|  
|Klikněte na...|Nastane, když po kliknutí na ovládacího prvku.|  
|TextChanged|Nastane, když se změní text textové pole nebo pole se seznamem.|  
|ItemsLoading|Nastane, když je kolekce položek ovládacího prvku požadoval Office. Office ukládá do mezipaměti kolekce položky dokud kódu změní vlastností ovládacího prvku, nebo zavoláte <xref:Microsoft.Office.Core.IRibbonUI.InvalidateControl%2A> metoda.|  
|ButtonClick|Nastane, když tlačítka na <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> nebo <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> po kliknutí na.|  
|SelectionChanged|Nastane při výběru v <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> nebo <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> změny.|  
|DialogLauncherClick|Nastane, když po kliknutí na ikonu pro spuštění dialogové okno v pravém dolním rohu skupiny.|  
  
 Obslužné rutiny události pro tyto události mají tyto dva parametry.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*Odesílatel*|<xref:System.Object> Představující ovládací prvek, který vyvolá událost.|  
|*e*|A <xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventArgs> obsahující <xref:Microsoft.Office.Core.IRibbonControl>. Tento ovládací prvek použít pro přístup k libovolné vlastnosti, které nejsou dostupné v modelu objektů pásu karet poskytované [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].|  
  
## <a name="see-also"></a>Viz také:  
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Aktualizace ovládacích prvků na pásu karet za běhu](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)   
 [Postupy: Přidání ovládacích prvků do zobrazení Backstage](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Postupy: zobrazení Add-in chyby uživatelského rozhraní](../vsto/how-to-show-add-in-user-interface-errors.md)  
 