---
title: "ListObject – ovládací prvek | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.Toolbox.List
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- lists, events
- ListObject control
- ListObject control, events
- ListObject control, data binding
- ListObject control, improving performance when bound to data
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2100a1c30fda5981d3d7e58f2f5077e0cdf87a2d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="listobject-control"></a>ListObject – ovládací prvek
  <xref:Microsoft.Office.Tools.Excel.ListObject> Je ovládací prvek seznamu, který zpřístupní události a mohou být vázány na data. Když přidáte seznam do listu, Visual Studio vytvoří <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který můžete ovládat přímo bez nutnosti procházení objektový model aplikace Microsoft Office Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="creating-the-control"></a>Vytvoření ovládacího prvku  
 Projekty na úrovni dokumentu, můžete přidat <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacích prvků na list v době návrhu nebo za běhu. Projekty doplňku VSTO, můžete přidat <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacích prvků do listů pouze za běhu. Další informace najdete v tématu [postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Ve výchozím nastavení, nejsou trvalé dynamicky vytvořený seznam objektů v listu jako umisťování ovládacích prvků při uzavření listu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="binding-data-to-the-control"></a>Vazba dat k ovládacímu prvku  
 A <xref:Microsoft.Office.Tools.Excel.ListObject> řízení podporuje jednoduché a komplexní datová vazba. <xref:Microsoft.Office.Tools.Excel.ListObject> Může být vázán k zdroje dat pomocí <xref:Microsoft.Office.Tools.Excel.ListObject.DataSource%2A> a <xref:Microsoft.Office.Tools.Excel.ListObject.DataMember%2A> vlastnosti v době návrhu nebo <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> metoda za běhu.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.ListObject> Se aktualizují automaticky, když je vázána na zdroj dat, jako například <xref:System.Data.DataTable>, který vyvolává při změně dat události. Pokud vytvoření vazby <xref:Microsoft.Office.Tools.Excel.ListObject> ke zdroji dat, který nevyvolá události při změně dat, musí volat <xref:Microsoft.Office.Tools.Excel.ListObject.RefreshDataRow%2A> nebo <xref:Microsoft.Office.Tools.Excel.ListObject.RefreshDataRows%2A> metoda aktualizace <xref:Microsoft.Office.Tools.Excel.ListObject>.  
  
 Když přidáte <xref:Microsoft.Office.Tools.Excel.ListObject> do buňky listu mapováním opakující se prvek schématu na dané buňky, Visual Studio automaticky mapuje <xref:Microsoft.Office.Tools.Excel.ListObject> generovaného datovou sadu. Ale <xref:Microsoft.Office.Tools.Excel.ListObject> není vázán automaticky data. Můžete provést kroky k vytvoření vazby <xref:Microsoft.Office.Tools.Excel.ListObject> do datové sady v době návrhu nebo za běhu v projektech na úrovni dokumentu. Prostřednictvím kódu programu můžete vázat <xref:Microsoft.Office.Tools.Excel.ListObject> k datové sadě za běhu v doplňku VSTO.  
  
 Protože data jsou oddělené od <xref:Microsoft.Office.Tools.Excel.ListObject>, měli byste přidat a odebrat data prostřednictvím vázané datovou sadu a ne přímo prostřednictvím <xref:Microsoft.Office.Tools.Excel.ListObject>. Pokud aktualizaci dat v datové sadě vázané prostřednictvím jakéhokoli mechanismu <xref:Microsoft.Office.Tools.Excel.ListObject> řízení automaticky změněn. Další informace najdete v tématu [vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Můžete rychle vyplnit <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku pomocí vytvoření vazby <xref:Microsoft.Office.Tools.Excel.ListObject> ke zdroji dat. Pokud upravíte data v vázaný na data <xref:Microsoft.Office.Tools.Excel.ListObject>, změny jsou automaticky vytvářeny v datovém zdroji. Pokud chcete, aby vyplnilo <xref:Microsoft.Office.Tools.Excel.ListObject> a potom povolit uživatelům změnit data v <xref:Microsoft.Office.Tools.Excel.ListObject> beze změny zdroje dat, můžete použít <xref:Microsoft.Office.Tools.Excel.ListObject.Disconnect%2A> metodu detach <xref:Microsoft.Office.Tools.Excel.ListObject> ze zdroje dat. Další informace najdete v tématu [postupy: vyplnění ovládacích prvků ListObject daty](../vsto/how-to-fill-listobject-controls-with-data.md).  
  
> [!NOTE]  
>  Datová vazba není podporována na překrývající se <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvky.  
  
### <a name="improving-performance-in-listobject-controls"></a>Zvýšení výkonu v ovládacích prvků ListObject  
 Čtení souboru XML do daty připojeného <xref:Microsoft.Office.Tools.Excel.ListObject> řízení obvykle být pomalejší, pokud nejprve vytvořit vazbu ovládacího prvku a pak zavolají <xref:System.Data.DataSet.ReadXml%2A> k vyplnění datové sady. Chcete-li zvýšit výkon, volejte <xref:System.Data.DataSet.ReadXml%2A> před vytvoření vazby ovládacího prvku.  
  
### <a name="disconnecting-listobject-controls-from-the-data-source"></a>Odpojení ovládacích prvků ListObject ze zdroje dat.  
 Po zadání <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku s daty pomocí vazby ke zdroji dat, můžete odpojit ho tak, aby se změny provedené v datech v seznamu objektu zdroje dat neovlivní. Další informace najdete v tématu [postupy: vyplnění ovládacích prvků ListObject daty](../vsto/how-to-fill-listobject-controls-with-data.md).  
  
### <a name="restoring-column-and-row-order"></a>Obnovení sloupec a pořadí řádků  
 Po vytvoření vazby dat <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek, který byl přidán do dokumentu v době návrhu, Visual Studio uchovává informace o pořadí sloupců a řádků vždy, když je sešit uložit. Pokud se uživatel přesune <xref:Microsoft.Office.Tools.Excel.ListObject> sloupců a řádků během běh, nové pořadí je zachováno při příštím otevření sešitu a <xref:Microsoft.Office.Tools.Excel.ListObject> řízení váže ke zdroji dat znovu.  
  
 Pokud chcete obnovit <xref:Microsoft.Office.Tools.Excel.ListObject> na jeho původní pořadí sloupců a řádků, můžete volat <xref:Microsoft.Office.Tools.Excel.ListObject.ResetPersistedBindingInformation%2A> metoda. Tato metoda odebere vlastní dokument vlastnosti související s sloupec a pořadí řádku zadaný <xref:Microsoft.Office.Tools.Excel.ListObject>. Volat tuto metodu z <xref:Microsoft.Office.Tools.Excel.Workbook.Shutdown> událostí sešitu, pokud nechcete, aby byla zachována pořadí sloupců a řádků <xref:Microsoft.Office.Tools.Excel.ListObject>.  
  
## <a name="formatting"></a>Formátování  
 Formátování, které lze použít pro <xref:Microsoft.Office.Interop.Excel.ListObject> lze použít pro <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku. To zahrnuje ohraničení, písma, číselném formátu a stylů. Koncoví uživatelé mohou Změna uspořádání sloupců v daty připojeném ovládacím <xref:Microsoft.Office.Tools.Excel.ListObject>, a tyto změny budou zachovat pomocí poskytnutého dokumentu <xref:Microsoft.Office.Tools.Excel.ListObject> byla přidána do dokumentu v době návrhu. Při příštím otevření dokumentu objekt seznamu budou vázána na stejném datovém zdroji, ale pořadí sloupců se projeví změny uživatelů.  
  
## <a name="adding-and-removing-columns-at-run-time"></a>Přidávání a odebírání sloupců v době běhu  
 Nelze ručně přidat nebo odebrat sloupce v vázaný na data <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku za běhu. Pokud koncový uživatel pokusí o odstranění sloupce, se okamžitě obnovit a budou odebrány všechny sloupce přidané. Proto je důležité si napsat kód pro vysvětlovat uživatelům, proč nemůžou provést tyto akce na <xref:Microsoft.Office.Tools.Excel.ListObject> vázané na data. Visual Studio obsahuje několik událostí <xref:Microsoft.Office.Tools.Excel.ListObject> související s datovou vazbu. Například můžete použít <xref:Microsoft.Office.Tools.Excel.ListObject.OriginalDataRestored> událost, která má upozornit uživatele, kteří se pokusili jste se odstranit data nelze odstranit a byla obnovena.  
  
## <a name="adding-and-removing-rows-at-run-time"></a>Přidávání a odebírání řádků v době běhu  
 Můžete ručně přidat a odebrat řádky v vázaný na data <xref:Microsoft.Office.Tools.Excel.ListObject> řídit, zadaný zdroj dat umožňuje přidání nové řádky a není určen jen pro čtení. Můžete například napsat kód ošetření událostí <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> ověřit data. Další informace najdete v tématu [postupy: ověření dat při přidání nového řádku do ovládacího prvku ListObject](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md).  
  
 Někdy relace objektu seznamu ke zdroji dat způsobí, že běžné chyby. Například můžete namapovat sloupce, které se má zobrazit v <xref:Microsoft.Office.Tools.Excel.ListObject>, takže pokud vynecháte sloupce, které mají omezení, jako je například pole, které nepovoluje hodnoty null, chyby jsou vyvolány pokaždé, když je vytvořen řádek. Můžete napsat kód přidejte chybějící hodnoty v obslužné rutiny události pro <xref:Microsoft.Office.Tools.Excel.ListObject.ErrorAddDataBoundRow> událostí.  
  
## <a name="renaming-listobject-controls-in-excel"></a>Přejmenování ovládacích prvků ListObject v aplikaci Excel  
 Umožňuje uživatelům změnit název tabulky aplikace Excel v době běhu pomocí aplikace Excel **návrhu** kartě. Ale <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek nepodporuje tuto funkci. Pokud se uživatel pokusí o přejmenování tabulky aplikace Excel, která odpovídá <xref:Microsoft.Office.Tools.Excel.ListObject>, název tabulky aplikace Excel se automaticky vrátí na původní název, když je sešit uložit.  
  
## <a name="events"></a>Události  
 Tyto události jsou k dispozici pro <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku:  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataBindingFailure>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataMemberChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataSourceChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Deselected>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.ErrorAddDataBoundRow>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.OriginalDataRestored>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.SelectedIndexChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.SelectionChange>  
  
## <a name="see-also"></a>Viz také  
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [Postupy: Přidání ovládacích prvků ListObject do listů](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Postupy: Změna velikosti ovládacích prvků ListObject](../vsto/how-to-resize-listobject-controls.md)   
 [Postupy: ověření dat při přidání nového řádku do ovládacího prvku ListObject](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)   
 [Postupy: mapování sloupců objektu ListObject na Data](../vsto/how-to-map-listobject-columns-to-data.md)   
 [Postupy: vyplnění ovládacích prvků ListObject daty](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Postupy: naplnění listů daty z databáze](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  