---
title: "Data v přizpůsobeních na úrovni dokumentu v mezipaměti | Microsoft Docs"
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
- data islands [Office development in Visual Studio]
- view [Office development in Visual Studio]
- caching data [Office development in Visual Studio], about caching data
- data caching [Office development in Visual Studio], about data caching
- data [Office development in Visual Studio], cache
- data [Office development in Visual Studio], document-level solutions
- document-level customizations [Office development in Visual Studio], data model
ms.assetid: 84808462-2c5d-4dc8-ab69-491d492b4a51
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: deb63265b65a382132d3ef957ad67ddd1bccb438
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cached-data-in-document-level-customizations"></a>Data uložená v mezipaměti v přizpůsobeních na úrovni dokumentu
  Primární cílem úpravy na úrovni dokumentů je oddělení dat ze zobrazení v dokumentech systému Office. Data odkazují na informace, které jsou uloženy v dokumentu, včetně čísla a text. Zobrazení odkazuje na uživatelské rozhraní a objektový model Microsoft Office Word a Microsoft Office Excel.  
  
 Visual Studio odděluje data ze zobrazení v přizpůsobeních na úrovni dokumentu povolením data vložit jako *data island*, také zavolat *datové mezipaměti*. Můžou číst nebo upravit data přímo, bez spuštění Word či Excel. To je užitečné, když potřebujete upravovat data v dokumentech na serveru, který nemá nainstalovanou sadu Microsoft Office. Word a Excel jsou určeny k použití v prostředí klienta; nejsou navrženy tak mohl být spuštěn na serveru.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Další informace o přizpůsobení na úrovni dokumentu najdete v tématu [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) a [architektura přizpůsobení na úrovni dokumentu](../vsto/architecture-of-document-level-customizations.md).  
  
## <a name="understanding-the-cached-data-programming-model"></a>Vysvětlení modelu programování Data uložená v mezipaměti  
 Island dat může obsahovat jakýkoli objekt ve vašem řešení, která splňuje určité požadavky. Tyto objekty zahrnují <xref:System.Data.DataSet> objekty, <xref:System.Data.DataTable> objekty a druhý objekt, který může serializovat <xref:System.Xml.Serialization.XmlSerializer> třídy. Další informace najdete v tématu najdete v části [ukládání dat do mezipaměti](../vsto/caching-data.md).  
  
 Zajistit zobrazení pro data uložená v mezipaměti můžete vázat ovládací prvky Windows Forms a *hostování ovládacích prvků* v dokumentu, který má objekty v data island. Datová vazba mezi ovládacími prvky vázané na data a data island zachová dvě synchronizovány. K datům, která je nezávislá ovládací prvky můžete také přidat ověřovacího kódu. Další informace najdete v tématu [vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Hostitelské ovládací prvky jsou rozšířené verze nativních objektů v objektové modely Excelu a Wordu. Na rozdíl od nativních objektů může být vázaný hostitelské ovládací prvky přímo na spravovaných datových objektů. Další informace najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md) a [ovládacích prvků Windows Forms na přehled dokumenty Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
## <a name="accessing-cached-data-on-the-server"></a>Přístup k datům v mezipaměti na serveru  
 Chcete-li získat přístup k data uložená v mezipaměti v dokumentu, můžete použít <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy. Tato třída je součástí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], a lze jej použít na serveru bez spuštěné aplikace Excel nebo Word. Když uživatel otevře dokument po úpravě data uložená v mezipaměti, všechny ovládací prvky vázané na data se automaticky synchronizují na změny a zobrazí se uživateli s aktualizovaná data. Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).  
  
 Excel a Word nejsou potřebná k zápisu dat na serveru, pouze k jejímu zobrazení na straně klienta. Excel a Word i nemusíte být nainstalována na serveru. To poskytuje lepší škálovatelnost a možnosti rychlého dávkového zpracování dokumentů, které obsahují datové ostrůvky.  
  
## <a name="data-caching-for-offline-use"></a>Ukládání dat do mezipaměti pro použití v offline režimu  
 Ukládání dat v data island umožňuje scénáře v režimu offline. Když uživatel poprvé otevře dokument nebo vyžádá dokumentu ze serveru, je data island vyplněn nejnovější data. Data island se uloží do mezipaměti v dokumentu a je k dispozici v režimu offline. Uživatel (a kódu), můžete upravit data, i když je k dispozici žádné aktivní připojení. Když se uživatel znovu připojí, změny dat přenášet zpět do zdroje dat serveru.  
  
## <a name="cached-data-and-custom-xml-parts-compared"></a>Data uložená v mezipaměti a vlastních částí XML porovnání  
 Vlastní části XML byly zavedeny v systému Microsoft Office 2007 jako způsob, jak uložit libovolný částí XML do dokumentu. I když jsou užitečné v mnoha stejné scénáře jako mezipaměť dat vlastní části XML, existují určité rozdíly mezi island dat a vlastní části XML. Další informace o vlastní části XML, najdete v části [Přehled vlastních částí XML](../vsto/custom-xml-parts-overview.md).  
  
 V následující tabulce jsou uvedeny některé rozdíly a podobnosti.  
  
||Mezipaměť dat|Vlastní části XML|  
|-|----------------|----------------------|  
|Aplikace Office, které můžete použít tyto?|Úpravy na úrovni dokumentů pro následující aplikace:<br /><br /> -Aplikace Excel<br />-Word|Řešení úrovni dokumentu a úrovni aplikace pro následující aplikace:<br /><br /> -Aplikace Excel<br />-PowerPoint<br />-Word|  
|Jaké typy dat můžete uložit?|Všechny veřejné objekt vaše přizpůsobení sestavení, která splňuje určité požadavky. Další informace najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md).|Žádná data XML.|  
|Můžete bez spuštění aplikace Microsoft Office přístup k datům?|Ano, pomocí <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třída poskytované [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].|Ano, s použitím třídy v <xref:System.IO.Packaging> obor názvů, nebo pomocí otevřete SDK formátu XML.|  
  
## <a name="see-also"></a>Viz také  
 [Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)   
 [Architektura řešení pro systém Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)  
  
  