---
title: "Schémata XML a Data v přizpůsobeních na úrovni dokumentu | Microsoft Docs"
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
- XML schemas [Office development in Visual Studio]
- schemas [Office development in Visual Studio]
- XML [Office development in Visual Studio], XML schemas
- XML schemas [Office development in Visual Studio], about XML schemas and data
- Office development in Visual Studio, XML
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: b3f55c8c6b2975e8dbaa85177fddcadaf62e000e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="xml-schemas-and-data-in-document-level-customizations"></a>Schémata XML a data v přizpůsobeních na úrovni dokumentu
  **Důležité** informace uvedené v tomto tématu týkající se aplikace Microsoft Word je vidění výhradně pro benefit a použití jednotlivce a organizace, kteří se nacházejí mimo Spojené státy a jeho území nebo který používáte, nebo vývoj programy, které běží na, produkty Microsoft Word, které byly před leden 2010, když Microsoft odebrat implementace konkrétní funkce licencí společnosti Microsoft týkající se vlastní kód XML z aplikace Microsoft Word. Tyto informace týkající se aplikace Microsoft Word nemusí přečteny nebo používány jednotlivce nebo organizace v USA nebo v jeho území, které používáte, nebo vývoj programy, které běží na produkty Microsoft Word, které byly licencí společnosti Microsoft po 10 leden 2010 ; tyto produkty nebudou chovají stejně jako produkty licencované před tímto datem nebo zakoupených a licenci na použití mimo Spojené státy.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Aplikace Microsoft Office Excel a Microsoft Office Word poskytují možnost mapování schémat na dokumenty. Tato funkce může zjednodušit import a export dat XML do/z dokumentu.  
  
 Visual Studio zpřístupňuje jako ovládacích prvků v programovací model mapovat prvky schématu v přizpůsobeních na úrovni dokumentu. Pro aplikaci Excel Visual Studio přidává podporu pro vytvoření vazby ovládacích prvků k datům v databázích, webové služby a objekty. Visual Studio pro Word a Excel, přidává podporu pro podokna akcí, které se dají použít s dokumentem mapované schématu pro vytvoření prostředí pro vaše řešení pro zlepšení činnosti koncových uživatelů. Další informace najdete v tématu [přehled podokna akcí](../vsto/actions-pane-overview.md).  
  
> [!NOTE]  
>  V řešení pro aplikaci Excel nelze použít s více částmi schémat XML.  
  
## <a name="objects-created-when-schemas-are-attached-to-excel-workbooks"></a>Objekty vytvořen při schémata jsou připojené do sešitů aplikace Excel  
 Pokud schéma připojit k sešitu, Visual Studio automaticky vytvoří několik objektů a přidá je do projektu. Tyto objekty by neměl odstranit pomocí nástrojů Visual Studio, protože jsou spravovaná aplikace Excel. Chcete odstranit, odeberte mapované prvky z listu nebo odpojit schématu pomocí nástrojů pro aplikaci Excel.  
  
 Existují dva hlavní objekty:  
  
-   Schéma XML (soubor XSD). Visual Studio pro každé schéma v sešitu, přidá do projektu schéma. Se zobrazuje jako položka projektu s příponou XSD v **Průzkumníku řešení**.  
  
-   Představuje zadaný <xref:System.Data.DataSet> třídy. Tato třída se vytvoří podle schématu. Tato třída datové sady se zobrazí na **zobrazení tříd**.  
  
## <a name="objects-created-when-schema-elements-are-mapped-to-excel-worksheets"></a>Objekty vytvořen při prvky schématu jsou namapované na listech aplikace Excel  
 Pokud namapujete element schema z **zdroj dat XML** podokna úloh do listu, Visual Studio automaticky vytvoří několik objektů a přidá je do projektu:  
  
-   Ovládací prvky. Pro každý objekt namapované v sešitu <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> řízení (pro prvky schématu bez opakování) nebo <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek (pro opakující se prvky schématu) je vytvořen v programovací model. <xref:Microsoft.Office.Tools.Excel.ListObject> Řízení lze odstranit pouze odstraněním mapování a namapované objekty ze sešitu. Další informace o ovládacích prvcích najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
-   BindingSource. Při vytváření <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> tak, že mapuje element schema bez opakování do listu, <xref:System.Windows.Forms.BindingSource> je vytvořena a <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládací prvek vázán <xref:System.Windows.Forms.BindingSource>. Je třeba svázat <xref:System.Windows.Forms.BindingSource> do instance zdroje dat, která odpovídá schématu namapované v dokumentu, jako je například instanci zadaného objektu <xref:System.Data.DataSet> třídu, která byla vytvořena. Vytvoření vazby, a to nastavením <xref:System.Windows.Forms.BindingSource.DataSource%2A> a <xref:System.Windows.Forms.BindingSource.DataMember%2A> vlastnosti, které jsou přístupné **vlastnosti** okno.  
  
    > [!NOTE]  
    >  <xref:System.Windows.Forms.BindingSource> Není vytvořena pro <xref:Microsoft.Office.Tools.Excel.ListObject> objekty. Musíte ručně vytvořit vazbu <xref:Microsoft.Office.Tools.Excel.ListObject> ke zdroji dat nastavením <xref:System.Windows.Forms.BindingSource.DataSource%2A> a <xref:System.Windows.Forms.BindingSource.DataMember%2A> vlastnosti v **vlastnosti** okno.  
  
### <a name="office-mapped-schemas-and-the-visual-studio-data-sources-window"></a>Office namapované schémata a okna zdrojů dat sady Visual Studio  
 Funkce namapované schématu systému Office a sady Visual Studio **zdroje dat** okno vám může pomoct prezentují data na listu aplikace Excel pro vytváření sestav, nebo úpravy. V obou případech můžete přetáhnout datové prvky na sešit aplikace Excel. Obě metody vytváření ovládacích prvků, které jsou data vázaná prostřednictvím <xref:System.Windows.Forms.BindingSource> ke zdroji dat, jako <xref:System.Data.DataSet> nebo webové službě.  
  
> [!NOTE]  
>  Pokud namapujete opakující se prvek schématu do listu, Visual Studio vytvoří <xref:Microsoft.Office.Tools.Excel.ListObject>. <xref:Microsoft.Office.Tools.Excel.ListObject> Není automaticky vázání na data prostřednictvím <xref:System.Windows.Forms.BindingSource>. Musíte ručně vytvořit vazbu <xref:Microsoft.Office.Tools.Excel.ListObject> ke zdroji dat nastavením <xref:System.Windows.Forms.BindingSource.DataSource%2A> a <xref:System.Windows.Forms.BindingSource.DataMember%2A> vlastnosti v **vlastnosti** okno.  
  
 V následující tabulce jsou uvedeny některé rozdíly mezi tyto dvě metody.  
  
|Schéma XML|okno Zdroje dat|  
|----------------|-------------------------|  
|Využívá rozhraní sady Office.|Používá **zdroje dat** oken v sadě Visual Studio.|  
|Umožňuje integrované funkce Office pro import a export dat ze souborů XML.|Musíte poskytnout import a export funkce prostřednictvím kódu programu.|  
|Musíte napsat kód k vyplnění generované ovládací prvky s daty.|Ovládací prvky přidají **zdroje dat** okno mají kód k vyplnění, společně s nezbytné připojovací řetězce při použití databázové servery, generuje automaticky.|  
  
## <a name="behavior-when-schemas-are-attached-to-word-documents"></a>Chování při schémata jsou připojené do dokumentů aplikace Word  
 Datové objekty nejsou vytvořeny, když připojíte schéma pro dokument aplikace Word, který se používá v projektech na úrovni dokumentu Office. Při mapování schématu elementu do dokumentu, jsou vytvořeny ovládací prvky. Typ ovládacího prvku, závisí na jaký typ elementu namapujete; opakující se elementy <xref:Microsoft.Office.Tools.Word.XMLNodes> a ovládacích prvků bez opakování generovat <xref:Microsoft.Office.Tools.Word.XMLNode> ovládací prvky. Další informace najdete v tématu [XmlNodes – ovládací prvek](../vsto/xmlnodes-control.md) a [XmlNode – ovládací prvek](../vsto/xmlnode-control.md).  
  
## <a name="deployment-of-solutions-that-include-xml-schemas"></a>Nasazení řešení, které zahrnují schémat XML  
 Měli byste vytvořit instalační program k nasazení řešení, které používá schéma XML, který je namapovaný na dokumentu. Instalační program měli zaregistrovat schématu v knihovně schématu v počítači uživatele. Pokud schéma nezaregistrujete, řešení budou i nadále fungovat, protože aplikace Word generuje dočasné schéma založené na prvky, které jsou v dokumentu, když uživatel otevře ji. Uživatel však nebudou moci provést ověření vůči nebo uložit schématu, která byla použita k vytvoření projektu. Další informace o instalačních programů najdete v tématu [nasazení aplikací, služeb a komponent](/visualstudio/deployment/deploying-applications-services-and-components).  
  
 Můžete také přidat kód do projektu, zkontrolujte, zda schéma je v knihovně a zaregistrovaná. Pokud není, je možné upozornit uživatele.  
  
 [!code-vb[Trin_VstcoreDataWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataWordVB/ThisDocument.vb#1)]
 [!code-csharp[Trin_VstcoreDataWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreDataWordCS/ThisDocument.cs#1)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: mapování schémat na dokumenty aplikace Word v sadě Visual Studio](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [Postupy: Mapování schémat na listy v prostředí Visual Studio](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)  
  
  