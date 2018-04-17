---
title: Ovládací prvky obsahu | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.DropDownListContentControl
- VST.Toolbox.RichTextContentControl
- VST.Toolbox.PlainTextContentControl
- VST.Toolbox.ComboBoxContentControl
- VST.Toolbox.CCBuildingBlockGalleryContentControl
- VST.Toolbox.DatePickerContentControl
- VST.Toolbox.PictureContentControl
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document building blocks [Office development in Visual Studio]
- restricted permissions [Office development in Visual Studio]
- ComboBoxContentControl class
- PictureContentControl class
- PlainTextContentControl class
- Office documents [Office development in Visual Studio], restricted permissions
- RichTextContentControl class
- content controls [Office development in Visual Studio]
- building block gallery [Office development in Visual Studio]
- controls [Office development in Visual Studio], content controls
- GroupContentControl class
- documents [Office development in Visual Studio], restricted permissions
- DropDownListContentControl class
- DatePickerContentControl class
- data binding [Office development in Visual Studio], content controls
- content controls [Office development in Visual Studio], about content controls
- custom XML parts, content controls
- templates [Office development in Visual Studio], content controls
- BuildingBlockGalleryContentControl class
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a1c56b7e48ce42699330e8eb40595d9cc761736e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="content-controls"></a>Ovládací prvky obsahu
  Ovládací prvky obsahu poskytnout způsob, jak vám na dokumentech návrhu a šablony, které mají tyto funkce:  
  
-   Uživatelské rozhraní (UI), která je řízena vstup jako formulář.  
  
-   Omezení, která uživatelům zabránit v úpravách chráněné oddíly dokumentu nebo šablony. Další informace najdete v tématu [ochrana částí z dokumentů pomocí ovládacích prvků obsahu](#Protection).  
  
-   Datová vazba ke zdroji dat. Další informace najdete v tématu [Data vytvoření vazby na ovládací prvky obsahu](#DataBinding).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [vazby dat do Wordu 2007 obsah ovládacích prvků pomocí Visual Studio Tools for Office System (3.0)](http://go.microsoft.com/fwlink/?LinkId=136785).  
  
## <a name="overview-of-content-controls"></a>Přehled ovládacích prvků obsahu  
 Ovládací prvky obsahu zadejte uživatelského rozhraní, která je optimalizovaná pro oba uživatele vstupní a tisku. Při přidání ovládacího prvku obsahu k dokumentu, je ovládací prvek určen ohraničení, název a dočasný text, který může poskytnout pokyny pro uživatele. Ohraničení a název ovládacího prvku se nezobrazí v tištěné verze dokumentu.  
  
 Například pokud chcete, aby uživatel zadal datum v části dokumentu, můžete přidat ovládací prvek obsahu pro výběr data v dokumentu. Když uživatel klikne na ovládací prvek, zobrazí se výběr standardní data uživatelského rozhraní. Můžete také nastavit vlastnosti ovládacího prvku nastavit místní kalendář, který se zobrazí a určit formát data. Po výběru datum, je skrytý rozhraní ovládacího prvku a pouze data se zobrazí, pokud uživatel vytiskne dokument.  
  
 Obsah – ovládací prvky také nápovědy, proveďte následující:  
  
-   Zabráníte uživatelům ve úpravy nebo odstranění části dokumentu. To je užitečné, pokud máte informace v dokumentu nebo šabloně, která uživatelé by měli být možné číst, ale nikoli upravovat, nebo pokud chcete, aby uživatelé mohli k úpravám ovládací prvky obsahu, ale nikoli jejich odstraňování.  
  
-   Vytvoření vazby části dokumentu nebo šablony k datům. Ovládací prvky obsahu můžete vázat na spravované objekty v databázi pole [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)], elementů XML, které jsou uložené v dokumentu a jiných zdrojů dat.  
  
 V projektech na úrovni dokumentu můžete přidat ovládací prvky obsahu dokumentu v době návrhu nebo za běhu. V doplňku VSTO projekty můžete přidat ovládací prvky obsahu pro všechny otevřené dokumenty v době běhu. Další informace najdete v tématu [postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
> [!NOTE]  
>  Ovládací prvky obsahu můžete použít pouze v dokumentech, které jsou uloženy ve formátu Open XML. Ovládací prvky obsahu nelze použít v dokumentech, které jsou uloženy ve formátu aplikace Word 97-2003 dokument (DOC).  
  
## <a name="types-of-content-controls"></a>Typy ovládacích prvků obsahu  
 Existují devět různé typy ovládacích prvků obsahu, které můžete přidat do dokumentů. Většina ovládacích prvků obsahu má odpovídající typ v <xref:Microsoft.Office.Tools.Word> oboru názvů. Můžete také použít obecný <xref:Microsoft.Office.Tools.Word.ContentControl>, což může představovat všechny dostupné ovládací prvky obsahu. Návod, jak využívat všechny dostupné ovládací prvky obsahu najdete v tématu [návod: vytváření šablony pomocí pomocí obsah ovládacích prvků](../vsto/walkthrough-creating-a-template-by-using-content-controls.md).  
  
### <a name="building-block-gallery"></a>Galerie stavebních bloků  
 Galerie stavebních bloků umožňuje uživatelům vybrat ze seznamu *stavební bloky dokumentu* vložit do dokumentu. Stavební blok dokumentu je obsahu, který byl vytvořen má být použit vícekrát, jako je například běžné titulní stránky, formátovaný tabulka nebo hlavičku. Další informace najdete v tématu <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> typu. Další informace o stavební bloky, najdete v části [co je nového pro vývojáře ve Wordu 2007](http://msdn.microsoft.com/en-us/74aa6688-65b3-4167-997d-131f26ad8f84).  
  
### <a name="check-box"></a>Zaškrtávací políčko  
 Zaškrtávací políčko poskytuje uživatelské rozhraní, která představuje binární stavu: zaškrtnuto nebo ne.  
  
 Na rozdíl od ostatních typů ovládacích prvků obsahu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] neposkytuje konkrétní typ, který reprezentuje obsahu ovládací prvek zaškrtávací políčko. Jinými slovy neexistuje žádný typ CheckBoxContentControl. Však můžete přesto vytvořit obsahu ovládací prvek zaškrtávací políčko přidáním obecný <xref:Microsoft.Office.Tools.Word.ContentControl> na dokument prostřednictvím kódu programu. Další informace najdete v tématu [obsahu ovládací prvky zaškrtávacích políček v projekty aplikace Word](#checkbox).  
  
### <a name="combo-box"></a>Pole se seznamem  
 Pole se seznamem zobrazí seznam položek, které mohou uživatelé vybrat. Na rozdíl od rozevíracího seznamu pole se seznamem umožňuje uživatelům přidat svoje vlastní položky. Další informace najdete v tématu <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> typu.  
  
### <a name="date-picker"></a>Výběr data  
 Výběr data poskytuje kalendář uživatelského rozhraní pro výběr data. Kalendář se zobrazí, když koncový uživatel klikne na šipku rozevíracího seznamu v ovládacím prvku. Můžete použít místní kalendáře a jiné datum formáty. Další informace najdete v tématu <xref:Microsoft.Office.Tools.Word.DatePickerContentControl> typu.  
  
### <a name="drop-down-list"></a>Rozevírací seznam  
 Rozevíracím seznamu se zobrazí seznam položek, které mohou uživatelé vybrat. Na rozdíl od pole se seznamem rozevíracím seznamu, uživatelé nebudou moci přidat nebo upravit položky. Další informace najdete v tématu <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> typu.  
  
### <a name="group"></a>Skupina  
 Ovládací prvek skupiny definuje oblasti chráněný dokument, který uživatelé se nedají upravit ani odstranit. Ovládacího prvku Skupina může obsahovat všechny položky dokumentů, například textu, tabulky, grafiky a jiných ovládacích prvků obsahu. Další informace najdete v tématu <xref:Microsoft.Office.Tools.Word.GroupContentControl> typu.  
  
### <a name="picture"></a>Obrázek  
 Ovládacího prvku obrázek zobrazuje bitovou kopii. Můžete určit bitovou kopii v době návrhu nebo čas spuštění, nebo mohou uživatelé kliknout tento ovládací prvek a vyberte obrázek, který chcete vložit do dokumentu. Další informace najdete v tématu <xref:Microsoft.Office.Tools.Word.PictureContentControl> typu.  
  
### <a name="rich-text"></a>Formátovaného textu  
 Ovládací prvek text ve formátu RTF obsahuje text nebo další položky, jako jsou tabulky, obrázky a další ovládací prvky obsahu. Další informace najdete v tématu <xref:Microsoft.Office.Tools.Word.RichTextContentControl> typu.  
  
### <a name="plain-text"></a>Prostý text  
 Ovládací prvek prostý text obsahuje text. Ovládací prvek prostý text nemůže obsahovat další položky, jako jsou tabulky, obrázky a další ovládací prvky obsahu. Kromě toho veškerý text v ovládacím prvku prostý text má stejné formátování. Například pokud můžete zobrazit v kurzívě jedno slovo věty, která je v ovládacím prvku prostý text, je kurzívou veškerého textu v ovládacím prvku. Další informace najdete v tématu <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> typu.  
  
### <a name="generic-content-control"></a>Obecné obsahu ovládacího prvku  
 Obecné obsahu ovládacího prvku <xref:Microsoft.Office.Tools.Word.ContentControl> objekt, který může představovat dostupné typy ovládacích prvků obsahu. Můžete změnit <xref:Microsoft.Office.Tools.Word.ContentControl> objekt se bude chovat, jako je jiného typu obsahu ovládacího prvku pomocí <xref:Microsoft.Office.Tools.Word.ContentControl.Type%2A> vlastnost. Například pokud vytvoříte <xref:Microsoft.Office.Tools.Word.ContentControl> objektů, představuje řízení jako prostý text, můžete ji změnit za běhu, aby se chová jako pole se seznamem.  
  
 Můžete vytvořit <xref:Microsoft.Office.Tools.Word.ContentControl> objekty pouze v době běhu, není v době návrhu. Další informace najdete v tématu [postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
## <a name="common-features-of-content-controls"></a>Běžné funkce ovládací prvky obsahu  
 Ovládací prvky nejvíce obsahu sdílet sadu členů, které můžete použít k provádění běžných úloh. Následující tabulka popisuje některé z úloh, které můžete provádět pomocí těchto členů.  
  
|K této úloze:|postupujte takto:|  
|--------------------|--------------|  
|Získání nebo nastavení text, který se zobrazí v ovládacím prvku.|Použití **Text** vlastnost. **Poznámka:** <xref:Microsoft.Office.Tools.Word.PictureContentControl> a <xref:Microsoft.Office.Tools.Word.ContentControl> typy nemají tuto vlastnost.|  
|Získání nebo nastavení dočasné text, který se zobrazí v ovládacím prvku, dokud uživatel upravuje ovládacího prvku, ovládacího prvku naplněný daty ze zdroje dat, nebo se odstraní obsah ovládacího prvku.|Použití **PlaceholderText** vlastnost. **Poznámka:** <xref:Microsoft.Office.Tools.Word.PictureContentControl> typ nemá tato vlastnost.|  
|Získání nebo nastavení produktu, který se zobrazí v ohraničení ovládacího prvku obsahu, když uživatel klikne ho.|Použití **název** vlastnost.|  
|Ovládací prvek z dokumentu automaticky odeberte po uživatel upravuje ovládacího prvku. (Text v ovládacím prvku zůstane v dokumentu.)|Použití **dočasné** vlastnost.|  
|Kód spusťte, když uživatel klikne na ovládací prvek obsahu, nebo když kurzor se přesune do ovládacího prvku obsahu prostřednictvím kódu programu.|Zpracování <xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering> události ovládacího prvku.|  
|Kód spusťte, když uživatel klikne na mimo ovládací prvek obsahu, nebo když kurzor je přesunut mimo ovládací prvek obsahu prostřednictvím kódu programu.|Zpracování <xref:Microsoft.Office.Tools.Word.ContentControlBase.Exiting> události ovládacího prvku.|  
|Po přidání ovládacího prvku obsahu v dokumentu v důsledku znovu spustit kód nebo operace vrácení zpět.|Zpracování <xref:Microsoft.Office.Tools.Word.ContentControlBase.Added> události ovládacího prvku.|  
|Spusťte kód bezprostředně před obsah ovládacího prvku se odstraní z dokumentu.|Zpracování <xref:Microsoft.Office.Tools.Word.ContentControlBase.Deleting> události ovládacího prvku.|  
  
##  <a name="Protection"></a> Ochrana částí dokumentů pomocí ovládacích prvků obsahu  
 Když chráníte část dokumentu, můžete zabránit uživatelům ve měnit nebo odstraňovat obsah v této části dokumentu. Existuje několik způsobů částí dokumentu, můžete chránit pomocí ovládacích prvků obsahu.  
  
 Pokud je oblast, kterou chcete chránit uvnitř ovládací prvek obsahu, můžete zabránit uživatelům ve úpravy nebo odstranění ovládacího prvku vlastností ovládacího prvku obsahu:  
  
-   **LockContents** vlastnost zabraňuje uživatelům upravovat obsah.  
  
-   **LockContentControl** vlastnost zabraňuje uživatelům v odstranění ovládacího prvku.  
  
 Pokud oblasti, které chcete chránit není uvnitř ovládací prvek obsahu, nebo pokud chcete chránit oblast, která obsahuje ovládací prvky obsahu a jiné typy obsahu, můžete umístit celou oblast <xref:Microsoft.Office.Tools.Word.GroupContentControl>. Na rozdíl od jiných ovládacích prvků obsahu <xref:Microsoft.Office.Tools.Word.GroupContentControl> neposkytuje žádné uživatelské rozhraní, které jsou viditelné pro uživatele. Jeho jediným účelem je určit oblasti, která uživatelé nemohou upravovat.  
  
> [!NOTE]  
>  Pokud vytvoříte <xref:Microsoft.Office.Tools.Word.GroupContentControl> obsahující vložený ovládací prvky obsahu, vložené ovládací prvky obsahu nejsou chráněna automaticky. Je nutné použít **LockContents** vlastnost jednotlivých vložených řízení uživatelům zabránit v úpravách jejich obsah.  
  
 Další informace o tom, jak Ochrana částí dokumentů pomocí ovládacích prvků obsahu najdete v tématu [postupy: ochrana částí z dokumentů pomocí ovládacích prvků obsahu](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md).  
  
##  <a name="DataBinding"></a> Vazba dat na ovládací prvky obsahu  
 Data můžete zobrazit v dokumentech pomocí vytvoření vazby ovládacího prvku obsahu ke zdroji dat. Při aktualizaci zdroje dat, obsah ovládacího prvku odráží změny. Také můžete uložit změny zpět do zdroje dat.  
  
 Ovládací prvky obsahu poskytují následující možnosti vazby dat:  
  
-   Ovládací prvky obsahu můžete vázat na pole databáze nebo spravovaných objektů s použitím stejného modelu vazby dat jako Windows Forms.  
  
-   Ovládací prvky obsahu můžete vázat na elementy v částí XML (i s názvem *vlastní části XML*) vložené do dokumentu.  
  
 Přehled vázání hostitelské ovládací prvky v řešeních pro systém Office s daty v tématu [vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
### <a name="using-the-windows-forms-data-binding-model"></a>Pomocí Windows Forms – datová vazba modelu  
 Ovládací prvky obsahu nejvíce podporovat model jednoduché datové vazby, který používá Windows Forms. Jednoduchá datová vazba znamená, že je ovládací prvek vázán do jednoho datového elementu, jako je například hodnotu ve sloupci tabulky data. Další informace najdete v tématu [datové vazby a rozhraní Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
 V projektech na úrovni dokumentu, můžete vázat data na ovládací prvky obsahu pomocí **zdroje dat** okno v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace o tom, jak přidat ovládací prvky vázané na data obsahu do dokumentů najdete v tématu [postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md) a [postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md).  
  
 Následující tabulka uvádí ovládací prvky obsahu, které můžete vázat na každý typ dat v **zdroje dat** okno.  
  
|Datový typ|Výchozí obsah ovládacího prvku|Další ovládací prvky obsahu, které mohou být vázány na tento datový typ|  
|---------------|-----------------------------|----------------------------------------------------------------|  
|<xref:System.Boolean><br /><br /> <xref:System.Byte><br /><br /> <xref:System.Char><br /><br /> <xref:System.Double><br /><br /> <xref:System.Enum><br /><br /> <xref:System.Guid><br /><br /> <xref:System.Int16><br /><br /> <xref:System.Int32><br /><br /> <xref:System.Int64><br /><br /> <xref:System.SByte><br /><br /> <xref:System.Single><br /><br /> <xref:System.String><br /><br /> <xref:System.TimeSpan><br /><br /> <xref:System.UInt16><br /><br /> <xref:System.UInt32><br /><br /> <xref:System.UInt64>|<xref:Microsoft.Office.Tools.Word.PlainTextContentControl>|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DatePickerContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|  
|<xref:System.DateTime>|<xref:Microsoft.Office.Tools.Word.DatePickerContentControl>|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PlainTextContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|  
|<xref:System.Drawing.Image><br /><br /> <xref:System.Byte> Pole|<xref:Microsoft.Office.Tools.Word.PictureContentControl>|Žádné|  
  
 Na úrovni dokumentu a projekty doplňku VSTO lze vázat ovládací prvek obsahu ke zdroji dat prostřednictvím kódu programu pomocí <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> metodu <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> vlastností ovládacího prvku. Pokud to uděláte, předejte v řetězci **Text** k *propertyName* parametr <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> metoda. **Text** je výchozí vlastnost vazby dat ovládacích prvků obsahu.  
  
 Ovládací prvky obsahu také podporují obousměrný datovou vazbu, ve kterém jsou aktualizovány změny v ovládacím prvku ke zdroji dat. Další informace najdete v tématu [postup: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
> [!NOTE]  
>  Ovládací prvky obsahu nepodporují rozšířené datové vazby. Pokud vytvoření vazby <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> nebo <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> ke zdroji dat pomocí datového modelu Windows Forms uživatelům se zobrazí pouze jednu hodnotu po kliknutí ovládací prvek. Pokud chcete tyto prvky svázat s sadu hodnot dat, které můžou uživatelé vybírat, můžete tyto ovládací prvky vázat na elementy ve vlastní část XML.  
  
### <a name="binding-content-controls-to-custom-xml-parts"></a>Vazba ovládacích prvků obsahu s vlastními částmi XML  
 Některé ovládací prvky obsahu můžete vázat na elementy ve vlastní části XML, které jsou vloženy do dokumentu. Další informace o vlastní části XML, najdete v části [Přehled vlastních částí XML](../vsto/custom-xml-parts-overview.md).  
  
 Chcete-li vytvořit vazbu ovládacího prvku obsahu pro element v na vlastní část XML, použijte **XMLMapping** vlastností ovládacího prvku. Následující příklad kódu ukazuje, jak vytvořit vazbu <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> k `Price` prvek v rámci `Product` uzlu na vlastní část XML, který již byl přidán k dokumentu.  
  
```vb  
plainTextContentControl1.XMLMapping.SetMapping("/Product/Price")  
```  
  
```csharp  
plainTextContentControl1.XMLMapping.SetMapping("/Product/Price", String.Empty, null);  
```  
  
 Návod, které ukazuje, jak k vytvoření vazby ovládacích prvků obsahu vlastní části XML v další podrobnosti najdete v tématu [návod: vytvoření vazby ovládacích prvků obsahu do vlastní části XML](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
 Při vytvoření vazby ovládacího prvku obsahu na vlastní část XML, obousměrný datová vazba je automaticky povolené. Pokud uživatel upravuje textu v ovládacím prvku, se automaticky aktualizují odpovídající elementy XML. Podobně pokud se změní hodnoty prvků v vlastní části XML ovládací prvky obsahu, které jsou vázány na elementy XML se zobrazí nová data.  
  
 Následující typy ovládacích prvků obsahu můžete vázat na vlastní části XML:  
  
-   <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.PictureContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>  
  
### <a name="data-binding-events-for-content-controls"></a>Datové vazby události pro ovládací prvky obsahu  
 Všechny ovládací prvky obsahu poskytují sadu událostí, které může zpracovat k provádění úloh souvisejících s daty, jako je například ověřování, že text v ovládacím prvku splňuje určitá kritéria, zdroj dat je aktualizována. Následující tabulka uvádí události obsahu ovládacích prvků, které se vztahují k datové vazby.  
  
|Úloha|Událost|  
|----------|-----------|  
|Spusťte kód bezprostředně před aplikace Word automaticky aktualizuje text v ovládacím prvku obsahu, který je vázaný na vlastní část XML.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.ContentUpdating>|  
|Spuštění kódu těsně před Word automaticky aktualizuje data v na vlastní část XML, který je vázaný na obsahu řídit (po změně textu v ovládacím prvku obsahu).|<xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating>|  
|Spuštění vlastního kódu k ověření obsah ovládacího prvku podle vlastních kritérií.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Validating>|  
|Spuštění kódu po úspěšně ověřen obsah ovládacího prvku.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Validated>|  
  
## <a name="limitations-of-content-controls"></a>Omezení ovládacích prvků obsahu  
 Pokud používáte ovládací prvky obsahu v projektech pro systém Office, pamatujte na následující omezení.  
  
### <a name="behavior-differences-between-design-time-and-run-time"></a>Rozdíly v chování návrhu a běhu  
 Mnoho omezení, která ukládá aplikace Microsoft Office Word na ovládací prvky obsahu v době běhu nejsou vynucená v době návrhu. Při návrhu řešení úrovni dokumentu v uživatelském rozhraní [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], nezapomeňte upravit ovládací prvky obsahu pouze způsoby, které jsou podporovány v době běhu.  
  
 Pokud upravíte obsah ovládacího prvku v době návrhu způsobem, který nepodporuje ovládacího prvku za běhu [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Návrhář nebude výstrahy nepodporované změny. Ale při ladění nebo spusťte projekt nebo pokud uložíte a projekt znovu otevřete, Word se zobrazí k chybě zprávy a žádosti o oprávnění k opravě dokumentu. Při opravě dokumentu aplikace Word odstraní všechny nepodporované obsahu a formátování z ovládacího prvku.  
  
 Například Word nezabrání můžete přidáním tabulky do <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> v době návrhu. Ale protože <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> objekty nemůže obsahovat tabulky v době běhu, Word se po otevření dokumentu zobrazí chybovou zprávu.  
  
 Všimněte si také, že mnoho vlastností, které definují chování ovládací prvky obsahu nemají žádný vliv v době návrhu. Například pokud nastavíte **LockContents** vlastnosti obsahu ovládacího prvku na **True** v době návrhu, můžete upravit text v ovládacím prvku v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] designer. Tato vlastnost pouze zabraňuje uživatelům v úpravy ovládacího prvku za běhu.  
  
### <a name="event-limitations"></a>Omezení událostí  
 Ovládací prvky obsahu neposkytují událost, která se vyvolá, když uživatel změní text nebo jiných položek v ovládacím prvku. Například není žádná událost, která se vyvolá, když uživatel vybere jinou položku v <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> nebo <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>.  
  
 Pokud chcete zjistit, když uživatel upravuje obsah ovládacího prvku typu obsahu, můžete vytvořit vazbu ovládacího prvku na vlastní část XML a pak zpracována <xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating> událostí. Tato událost se vyvolá, když uživatel změní obsah ovládacího prvku, který je vázaný na vlastní část XML. Návod, který ukazuje, jak vytvořit vazbu ovládacího prvku obsahu na vlastní část XML, najdete v části [návod: vytvoření vazby ovládacích prvků obsahu do vlastní části XML](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
###  <a name="checkbox"></a> Ovládací prvky obsahu zaškrtněte políčko v projekty aplikace Word  
 Word 2010 zavedl nový typ obsahu ovládacího prvku, který představuje zaškrtávací políčko. Ale [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] neposkytuje odpovídající typ CheckBoxContentControl budete moci použít v projektech Office. Vytvořit obsahu ovládací prvek zaškrtávací políčko v [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] nebo Wordu 2010, project, použijte <xref:Microsoft.Office.Tools.Word.ControlCollection.AddContentControl%2A> metodu pro vytvoření <xref:Microsoft.Office.Tools.Word.ContentControl> objektu a předat <xref:Microsoft.Office.Interop.Word.WdContentControlType.wdContentControlCheckBox> hodnota metodě pro určení obsahu ovládací prvek zaškrtávací políčko. Následující příklad kódu ukazuje, jak to udělat.  
  
 [!code-vb[Trin_ContentControlReference#800](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/checkbox.vb#800)]
 [!code-csharp[Trin_ContentControlReference#800](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/checkbox.cs#800)]  
  
## <a name="see-also"></a>Viz také  
 [Automatizace v aplikaci Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Postupy: Přidání ovládacích prvků obsahu do dokumentů aplikace Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Návod: Vytvoření šablony s použitím ovládacích prvků obsahu](../vsto/walkthrough-creating-a-template-by-using-content-controls.md)   
 [Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)   
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
