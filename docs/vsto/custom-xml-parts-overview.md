---
title: "Vlastní XML částí Přehled | Microsoft Docs"
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
- custom XML parts [Office development in Visual Studio], about
- Office Open XML Formats [Office development in Visual Studio]
- custom XML parts [Office development in Visual Studio]
- embedding XML data in documents [Office development in Visual Studio]
- XML parts [Office development in Visual Studio]
- XML file formats [Office development in Visual Studio]
- data [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- XML [Office development in Visual Studio], custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- documents [Office development in Visual Studio], custom XML parts
ms.assetid: a14119dc-59e8-4614-94f1-08c92bdf7300
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 735660c3af1c0a8792a35981788b70f4a79d55b1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="custom-xml-parts-overview"></a>Přehled vlastních částí XML
  Můžete vložit XML data v dokumentech pro některé aplikace Microsoft Office. Když vložíte XML data v dokumentu, lze data s názvem *vlastní část XML*.  
  
 Můžete vytvořit a upravit vlastní části XML v dokumentu pomocí doplňku VSTO nebo na úrovni dokumentu řešení v sadě Visual Studio. Není nutné ke spuštění aplikace Microsoft Office vytvářet a upravovat vlastní části XML.  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty na úrovni dokumentu a projekty doplňku VSTO pro Excel, PowerPoint a Word. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  
  
> [!NOTE]  
>  Visual Studio můžete také do mezipaměti datové objekty v přizpůsobeních na úrovni dokumentu. Tato funkce se liší od vlastní části XML, i když jsou některé podobnosti. Další informace najdete v tématu [Data do mezipaměti v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md).  
  
## <a name="understanding-custom-xml-parts"></a>Seznámení s vlastními částmi XML  
 Vlastní části XML byly zavedeny v systému Microsoft Office 2007, společně s otevřeného formátu XML. Tyto formáty jsou nové formáty souborů XML pro Excel, PowerPoint a Word (například XLSX, PPTX a .docx). Skládají dokumenty v tyto formáty souborů XML (i s názvem *částí XML*), jsou uspořádány do složky v archivu ZIP. Většina částí XML jsou předdefinované částí, které vám pomohou definovat strukturu a stav dokumentu. Dokumenty však může také obsahovat vlastní části XML, které můžete použít k uložení libovolná data XML v dokumentech.  
  
 Formáty souborů XML umožňují aplikace pro práci s dokumenty způsoby, které nejsou možné ve starších formátech binárního souboru (například XLS, PPT a .doc). Všechny aplikace, který může číst archivy ZIP můžete zkontrolovat a změnit obsah dokumentů, i když není nainstalována aplikace Microsoft Office.  
  
 Další informace o struktuře Open XML a vlastní části XML najdete v následujících článcích:  
  
-   [Představení formáty souborů Office (2007) Open XML](http://msdn.microsoft.com/en-us/96018532-f62c-4da7-bbff-16b96a483fbf)  
  
-   [Postupy: manipulace s dokumenty formáty Open XML](http://msdn.microsoft.com/en-us/c989d4e2-053d-4e1f-83be-257c608b343f)  
  
-   [Návod: Slova 2007 XML formátu](http://msdn.microsoft.com/en-us/fc1afcb2-27fb-4608-9f29-11b7bd23ea4a)  
  
-   [Vytváření dokumentů aplikace Word 2007 pomocí Open XML formáty](http://msdn.microsoft.com/en-us/59a46f4e-5a5a-4dac-86e5-7dfd43330766)  
  
> [!NOTE]  
>  Aplikace Excel, Word a PowerPoint také umožní používat vlastní části XML do dokumentů, které jsou uloženy ve formátech binární soubor. Ale pokud dokument je uložen v binárním formátu, můžete nelze přidávat nebo upravovat vlastní části XML bez spuštění aplikace Microsoft Office.  
  
## <a name="creating-and-modifying-custom-xml-parts"></a>Vytvoření a úprava vlastních částí XML  
 Můžete vytvářet nebo upravovat vlastní části XML, když je dokument otevřít v aplikaci Office, nebo při zavření v dokumentu – i když není nainstalována aplikace Microsoft Office.  
  
### <a name="modifying-xml-parts-while-the-office-application-is-running"></a>Úprava částí XML je spuštěna aplikace Office  
 Vlastní části XML můžete pracovat s použitím přizpůsobení na úrovni dokumentu nebo doplňku VSTO. Pokud používáte přizpůsobení na úrovni dokumentu, je většinou pracují s vlastní části XML, které jsou v přizpůsobené dokumentu. Pokud používáte doplňku VSTO, můžete vytvářet nebo upravovat vlastní části XML v jakékoli dokument, který je otevřený v aplikaci.  
  
 Pokud chcete vytvořit vlastní část XML pomocí sady Visual Studio, přidejte nový <xref:Microsoft.Office.Core.CustomXMLPart> k <xref:Microsoft.Office.Core.CustomXMLParts> kolekce v dokumentu. Další informace naleznete v následujících tématech:  
  
-   [Postupy: Přidání vlastních částí XML do přizpůsobení na úrovni dokumentu](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)  
  
-   [Návody: Přidání vlastních částí XML do dokumentů s použitím doplňků VSTO](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)  
  
### <a name="modifying-xml-parts-without-starting-the-office-application"></a>Úprava částí XML bez spuštění aplikace Office  
 Můžete přidat nebo upravit vlastní část XML bez spuštění aplikace Excel, PowerPoint nebo Word. To je užitečné, pokud chcete pracovat s daty XML v dokumentu v počítači, který nemá nainstalován, například server aplikace Microsoft Office.  
  
 Pokud chcete přidat vlastní část XML bez spuštění aplikace Microsoft Office, použijte třídy v sadě SDK Open XML. Tyto třídy jsou navržená k poskytování přístupu k obsahu Open XML, které jsou specifické pro dokumenty Office. Například pokud chcete přidat vlastní část XML do sešitu aplikace Excel, můžete použít [AddNewPart\<T >](http://msdn.microsoft.com/en-us/47c348c0-77ab-a504-5097-bcd6a213921a) metodu [WorkbookPart](http://msdn.microsoft.com/en-us/d011e6f4-77dd-d02d-66ef-dc4a9e7b26f2) objektu. Další informace najdete v tématu [Open XML SDK 2.0](http://msdn.microsoft.com/en-us/f6a9ae68-7989-4208-97f5-3c945137a0ab).  
  
## <a name="binding-custom-xml-parts-to-word-content-controls"></a>Vytvoření vlastních částí XML vazby na ovládací prvky obsahu aplikace Word  
 Ovládací prvky obsahu v aplikaci Word řešení můžete vázat na elementy ve vlastní část XML. Pokud ovládací prvek obsahu je vázán na vlastní část XML, data ve vlastní část XML se zobrazí v uživatelském rozhraní (UI) obsahu ovládacího prvku. Pokud uživatel upravuje textu v ovládacím prvku, se automaticky aktualizuje odpovídající element XML. Podobně změnu hodnoty prvků v vlastní části XML ovládací prvky obsahu, které jsou vázány na elementy XML zobrazí nová data. Další informace najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md).  
  
## <a name="see-also"></a>Viz také  
 [Schémata XML a Data v přizpůsobeních na úrovni dokumentu](../vsto/xml-schemas-and-data-in-document-level-customizations.md)   
 [Postupy: Přidání vlastních částí XML do přizpůsobení na úrovni dokumentu](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md)   
 [Postupy: Přidání vlastních částí XML do dokumentů s použitím doplňků VSTO](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)   
 [Ovládací prvky obsahu](../vsto/content-controls.md)   
 [Návod: Vazba ovládacích prvků obsahu s vlastními částmi XML](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md)  
  
  