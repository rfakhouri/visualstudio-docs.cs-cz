---
title: Ovládací prvky Windows Forms na přehled dokumenty sady Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- old data showing in error [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], Word
- Windows Forms controls [Office development in Visual Studio], adding
- Windows Forms controls [Office development in Visual Studio], arranging
- data [Office development in Visual Studio], old data showing in error
- user controls [Office development in Visual Studio], Windows Forms
- Windows Forms controls [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], removing
- application development [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], Windows Forms controls
- Office [Office development in Visual Studio], Windows Forms controls
- Office documents [Office development in Visual Studio, controls
- documents [Office development in Visual Studio], Windows Forms controls
- document-level customizations [Office development in Visual Studio], Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], about Windows Forms controls
- Office applications [Office development in Visual Studio], Windows Forms
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a8ac517153555b6e18726d7343b510c68533117a
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258707"
---
# <a name="windows-forms-controls-on-office-documents-overview"></a>Ovládací prvky Windows Forms na přehled dokumenty sady Office
  Windows Forms – ovládací prvky jsou objekty, které mohou uživatelé komunikovat s zadejte nebo pracovat s daty. V projektech na úrovni dokumentu pro aplikaci Microsoft Office Excel a Microsoft Office Word můžete přidat ovládací prvky Windows Forms k dokumentu nebo sešitu ve vašem projektu v době návrhu nebo prostřednictvím kódu programu přidáním těchto ovládacích prvků za běhu. Tyto ovládací prvky můžete přidat pro aplikaci Excel nebo Word prostřednictvím kódu programu pro všechny otevřené dokumenty a list za běhu v doplňku VSTO.  
  
 Další informace najdete v tématu [postupy: Přidání Windows Forms – ovládací prvky do dokumentů Office](../vsto/how-to-add-windows-forms-controls-to-office-documents.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="use-windows-forms-controls"></a>Pomocí ovládacích prvků Windows Forms  
 Můžete přidat ovládací prvky Windows Forms do dokumentů a prvky přizpůsobitelné uživatelského rozhraní (UI), včetně podokna akcí, vlastních podoken úloh a Windows Forms. Ovládací prvky Windows Forms obvykle mají stejné chování na dokumentech jako na tyto další prvky uživatelského rozhraní, ale existují určité rozdíly. Informace najdete v tématu [omezení Windows Forms – ovládací prvky v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md).  
  
 Rozhodnutí, jestli se má přidat do dokumentu nebo jiného elementu uživatelského rozhraní Windows Forms – ovládací prvky závisí na několika faktorech. Při navrhování uživatelského rozhraní vašeho řešení, zvažte použití ovládacích prvků Windows Forms, jak je popsáno v následující tabulce.  
  
 V dokumentu.  
 -   Pokud chcete zobrazit ovládací prvky 100 % času.  
  
-   Pokud chcete uživatelům zadat data přímo v dokumentu, například v založené na formulářích dokumentech, kde je pevně nastavené prostor pro úpravy.  
  
-   Když chcete ovládacích prvků pro zobrazení souladu data v dokumentu. Například při přidávání tlačítek na každý řádek objekt seznamu, je vhodné je souladu jednotlivé položky seznamu.  
  
 V podokně Akce nebo vlastního podokna úloh.  
 -   Pokud byste chtěli poskytnout kontextové informace pro uživatele.  
  
-   Pokud chcete výsledky zobrazí v dokumentu a ne dotazu ovládací prvky a data.  
  
-   Pokud chcete zajistit, aby ovládací prvky nejsou vytiskne dokument.  
  
-   Pokud chcete zajistit, že ovládací prvky nezpůsobují konflikt za dokumentu.  
  
 Ve formuláři Windows.  
 -   Pokud chcete řídit velikost uživatelského rozhraní.  
  
-   Pokud chcete zabránit uživatelům ve skrytí nebo odstranění ovládacích prvků.  
  
-   Pokud chcete získat vstup od uživatele a zabrání žádné v dokumentu činnosti, dokud není přijata vstup uživatele.  
  
## <a name="add-windows-forms-controls-programmatically"></a>Přidání ovládacích prvků Windows Forms prostřednictvím kódu programu  
 Můžete přidat ovládací prvky Windows Forms do dokumentů aplikace Word a sešitů aplikace Excel za běhu. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Poskytuje pomocné metody pro přidání většiny běžných ovládacích prvků Windows Forms. Tyto pomocné metody umožňují rychle přidáte k dokumentu systému Office a přístup kombinuje funkce ovládacího prvku Windows Forms – ovládací prvky a funkce Office související těchto ovládacích prvků.  
  
 Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="use-windows-forms-controls-in-document-level-projects"></a>Pomocí ovládacích prvků Windows Forms v projekty na úrovni dokumentu  
 Některé aspekty pomocí ovládacích prvků Windows Forms v dokumentech jsou jedinečné pro projekty na úrovni dokumentu, které vám umožní návrh uživatelského rozhraní dokumentu pomocí návrháře Visual Studio.  
  
### <a name="create-custom-user-controls"></a>Vytvořit vlastní uživatelské ovládací prvky  
 Můžete přidat uživatelský ovládací prvek do projektu a přidat jej do **sada nástrojů**. Potom můžete přetáhnout uživatelského ovládacího prvku přímo do vašeho dokumentu stejným způsobem, jako by přidání ovládacího prvku Windows Forms do dokumentu. Existují některé věci, třeba vzít v úvahu při vytváření uživatelských ovládacích prvků:  
  
-   Nevytvářejte **zapečetěné** uživatelský ovládací prvek. Při přetažení ovládacího prvku do dokumentu, Visual Studio generuje obálkovou třídu odvozenou z ovládacího prvku uživatel ji rozšířit a podpoře jeho použití na dokumentu. Pokud je uživatelský ovládací prvek **zapečetěné**, Visual Studio nelze generovat obálkovou třídu.  
  
-   Uživatelské ovládací prvky, musí mít <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut nastaven na **true**. Uživatelské ovládací prvky vytvářet v projektu aplikace Office mají tento atribut nastavit na **true** ve výchozím nastavení, ale uživatelské ovládací prvky, které jsou součástí mimo projekty nemusí mít tento atribut nastavit na **true**.  
  
-   Po přidání uživatelského ovládacího prvku v dokumentu, nepřejmenovávejte ani odstranit <xref:System.Windows.Forms.UserControl> třídy z projektu. Pokud potřebujete změnit název uživatelského ovládacího prvku musíte nejprve odstranit z dokumentu a poté ji znovu přidejte po změně názvu.  
  
### <a name="arrange-controls-at-design-time"></a>Uspořádání ovládacích prvků v době návrhu  
 Pokud přidáte více ovládacích prvků do dokumentů aplikace Word a Excel v době návrhu, můžete rychle nastavit zarovnání všech vybraných ovládacích prvků pomocí **aplikace Microsoft Office Word** a **aplikace Microsoft Office Excel**panely nástrojů v sadě Visual Studio. Panely nástrojů jsou k dispozici jenom v případě, že je dokument nebo listu je otevřený v návrháři.  
  
 Když vyberete více ovládacích prvků v návrháři, můžete na těchto panelech nástrojů tlačítka následující k uspořádání ovládacích prvků:  
  
-   **Zarovnat doleva**  
  
-   **Zarovnat Center**  
  
-   **Zarovnat práva**  
  
-   **Zarovnat nahoru**  
  
-   **Zarovnat středy**  
  
-   **Zarovnat dolů**  
  
-   **Stejné vodorovné mezery**  
  
-   **Stejné svislé mezery**  
  
> [!NOTE]  
>  Tato tlačítka v projekty aplikace Word, jsou povolena pouze v případě, že vybraný ovládací prvky nejsou v textu. Ovládací prvky, které přidáte do dokumentu v době návrhu jsou ve výchozím nastavení v textu.  
  
### <a name="prevent-old-data-from-appearing-in-excel-workbooks-during-loading"></a>Zabránit zobrazování v sešitech aplikace Excel během načítání stará data  
 Když přidáte ovládací prvky Windows Forms do dokumentů nebo listů v době návrhu, zůstanou ovládacích prvků v dokumentu, při zavření v dokumentu. Ovládací prvky přidané v době návrhu se také nazývají *statické ovládací prvky*.  
  
 Po otevření sešitu aplikace Excel, která obsahuje statické ovládací prvky sešit zobrazí bitové mapy ovládacího prvku v ovládacím prvku ActiveX, dokud přizpůsobení kód spustí a načte skutečný ovládací prvek. Aplikace Excel vytvoří tento rastrový obrázek a ukládá je v sešitu vždy, když je sešit uložit. Bitmapy ukazuje ovládacího prvku ukázalo se při posledním uložení sešitu, včetně všechna data, která byla zobrazení ovládacího prvku. Další informace o ovládací prvek ActiveX, který obsahuje ovládací prvky Windows Forms a rastrové obrázky, naleznete v části [omezení Windows Forms – ovládací prvky v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md).  
  
 V určitých podmínek kód nenačte a se zobrazí pouze rastrového obrázku, například když uživatel otevře sešit v režimu návrhu. Navíc pokud uživatel otevře sešit v počítači, který nemá [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] nainstalována, přizpůsobení nelze spustit na načíst ovládací prvky, a proto je viditelná pouze bitové mapy ovládacího prvku. Vždy byste měli odebrat osobní informace z ovládacích prvků na sešity před uložením sešit a odesílání do jiného uživatele, ujistěte se, že vaše osobní údaje neodhalí omylem.  
  
### <a name="match-control-size-to-cell-size-on-an-excel-worksheet"></a>Velikost ovládacího prvku shodu tak, aby velikost buňky listu aplikace Excel  
 Můžete nastavit na změnu velikosti automaticky při změně velikosti nadřazené buňce ovládacího prvku. Další informace najdete v tématu [postupy: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md).  
  
### <a name="add-components-that-are-shared-by-all-worksheets"></a>Přidat součásti, které jsou sdíleny všech listů  
 Můžete přidat součásti, které chcete sdílet mezi všechny listy, například <xref:System.Data.DataSet>, k sešitu Designer místo do listů. Součást se zobrazí na panelu součásti.  
  
### <a name="formula-for-embedding-controls-on-an-excel-worksheet"></a>Vzorec pro vložení ovládacích prvků na listu aplikace Excel  
 Když vyberete ovládacího prvku v aplikaci Excel, uvidíte **=EMBED("WinForms.Control.Host","")** v **řádek vzorců**. Tento text je nezbytné a nesmí být odstraněna.  
  
### <a name="layout-style-of-controls-on-a-word-document"></a>Stylu rozložení ovládacích prvků na dokument aplikace Word  
 Při přidání ovládacího prvku na dokument aplikace Word v projektech na úrovni dokumentu pomocí sady Visual Studio návrháře ovládací prvek přidán v textu. Změna stylu rozložení ovládacího prvku, klikněte pravým tlačítkem na ovládací prvek a potom klikněte na **formát ovládacího prvku**. Vyberte styl zabalení na **rozložení** stránky **formát objektu** dialogové okno.  
  
 Když přidáte ovládacího prvku dokument aplikace Word v době běhu, můžete zadat stylu rozložení nového ovládacího prvku s použitím různých `Add` \< *třídu ovládacího prvku*> z přetížení metody <xref:Microsoft.Office.Tools.Word.ControlCollection> – třída:  
  
-   Přidání ovládacího prvku v textu, použijte přetížení, které přijímá <xref:Microsoft.Office.Interop.Word.Range> , určuje umístění ovládacího prvku.  
  
-   Přidání ovládacího prvku jako plovoucí obrazce, použijte přetížení, které přijímá souřadnice levého a horního ovládacího prvku.  
  
 Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Pokud otevřete šablonu aplikace Word v návrháři Visual Studio, ovládací prvky bez vložené v šabloně nemusí být vidět, protože Visual Studio otevře šablonu v **normální** zobrazení. Chcete-li zobrazit ovládací prvky, změnit zobrazení na **rozložením při tisku**.  
  
### <a name="controls-outside-the-main-document-body"></a>Ovládací prvky mimo těla hlavní dokumentu  
 Windows Forms – ovládací prvky nejsou podporovány v záhlaví nebo zápatí stránky, nebo v rámci vnořeného dokumentu.  
  
### <a name="add-components-at-design-time"></a>Přidat součásti v době návrhu  
 Některé ovládací prvky nebo součásti nejsou viditelné v dokumentu a místo toho se zobrazí na panelu součásti. Visual Studio poskytuje panelu součásti pro každý okna dokumentu. Součást panelu se zobrazí na obrazovce pouze v případě, že součásti existovat v dokumentu.  
  
## <a name="see-also"></a>Viz také:  
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Ovládací prvky Windows Forms](/dotnet/framework/winforms/controls/index)   
 [Omezení ovládacích prvků Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)   
 [Postupy: Přidání ovládacích prvků Windows Forms do dokumentů Office](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Postupy: Změna velikosti ovládacích prvků v buňkách listu](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [Postupy: skrytí ovládacích prvků na listech při tisku](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [Návod: Změna formátování listů s použitím ovládacích prvků CheckBox](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)   
 [Návod: Změna formátování dokumentů s použitím ovládacích prvků CheckBox](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md)   
 [Návod: Zobrazení textu v textovém poli na listu s použitím tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)   
 [Návod: Zobrazení textu v textovém poli v dokumentu s použitím tlačítka](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md)   
 [Omezení ovládacích prvků Windows Forms v dokumentech Office](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)   
 [Návod: Aktualizace grafu v dokumentu s použitím přepínačů](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md)   
 [Návod: Aktualizace grafu na listu s použitím přepínačů](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)  
  
  