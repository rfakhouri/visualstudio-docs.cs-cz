---
title: "Ukládání dat do mezipaměti | Microsoft Docs"
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
- data caching [Office development in Visual Studio], about caching data
- data [Office development in Visual Studio], caching
- data caching [Office development in Visual Studio]
ms.assetid: 6f34251e-7d31-4f2b-ac17-42fd2837c626
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0d5f044f1f1d0f36918939a67d9d2e5bb1899929
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="caching-data"></a>Ukládaní dat do mezipaměti
  Datové objekty v přizpůsobení na úrovni dokumentu můžete mezipaměti, takže data jsou přístupné v režimu offline, nebo bez otevření aplikace Microsoft Office Word nebo Microsoft Office Excel. Pro ukládání do mezipaměti objekt, objekt musí mít datový typ, který splňuje určité požadavky. Mnoho běžné typy dat v rozhraní .NET Framework splňovat tyto požadavky, včetně <xref:System.String>, <xref:System.Data.DataSet>, a <xref:System.Data.DataTable>.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Existují dva způsoby, jak přidat objekt do mezipaměti dat:  
  
-   Přidání objektu do mezipaměti dat, když je integrované řešení, použít <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut deklarace objektu. Další informace najdete v tématu [postup: Data do mezipaměti pro použití v režimu Offline nebo na serveru](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   K přidání objektu do datové mezipaměti prostřednictvím kódu programu za běhu, použijte `StartCaching` metoda hostitele položky, jako `ThisDocument` nebo `ThisWorkbook` třídy. Další informace najdete v tématu [postup: mezipaměti prostřednictvím kódu programu zdroj dat v dokumentu systému Office](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md).  
  
 Po přidání objektu do datové mezipaměti, můžete přístup a upravit data uložená v mezipaměti bez spuštění Word či Excel. Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).  
  
## <a name="requirements-for-data-objects-to-be-cached"></a>Požadavky pro datové objekty do mezipaměti  
 Pro ukládání do mezipaměti objekt dat ve vašem řešení, objekt musí splňovat tyto požadavky:  
  
-   Být pro čtení a zápis veřejné pole nebo vlastnost položku hostitele, jako `ThisDocument` nebo `ThisWorkbook` třídy.  
  
-   Není možné indexer nebo jiných Parametrizovaná vlastnost.  
  
 Kromě toho musí být serializovatelný podle datový objekt <xref:System.Xml.Serialization.XmlSerializer> třídy, což znamená typ objektu musí mít tyto vlastnosti:  
  
-   Být veřejného typu.  
  
-   Máte veřejný konstruktor bez parametrů.  
  
-   Není spustit kód, který vyžaduje další bezpečnostní oprávnění.  
  
-   Vystavení pouze pro čtení a zápis veřejné vlastnosti (ostatní vlastnosti bude ignorován).  
  
-   Není vystavit vícerozměrných polí (jsou podmínky přijaty vnořených polí).  
  
-   Nevrací rozhraní z vlastnosti a pole.  
  
-   Implementováno <xref:System.Collections.IDictionary> Pokud kolekce.  
  
 Když mezipaměti na datový objekt [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] serializuje do formátu řetězce XML, který je uložený v objektu *vlastní část XML* v dokumentu. Další informace najdete v tématu [přehled částí XML vlastní](../vsto/custom-xml-parts-overview.md).  
  
## <a name="cached-data-size-limits"></a>Omezení velikosti Data uložená v mezipaměti  
 Existují některá omezení na celkovém množství dat, které můžete přidat do mezipaměti data v dokumentu a velikost všech jednotlivých objektu v datové mezipaměti. Pokud tato omezení překročí, aplikaci dojít k neočekávaném zavření při uložení dat do mezipaměti data.  
  
 Abyste se vyhnuli tyto limity, postupujte podle následujících pokynů:  
  
-   Nepřidávejte do mezipaměti dat všech objektů, které jsou větší než 10 MB.  
  
-   Nepřidávejte více než 100 MB celková data do mezipaměti dat do jednoho dokumentu.  
  
 Toto jsou přibližné hodnoty. Přesný omezení závisí na několika faktorech, jako dostupné paměti RAM a počet spuštěných procesů.  
  
## <a name="controlling-the-behavior-of-cached-objects"></a>Řízení chování v mezipaměti objektů  
 Získat lepší kontrolu nad chováním objektu v mezipaměti, můžete implementovat <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> rozhraní pro typ objektu v mezipaměti. Například můžete implementovat toto rozhraní, pokud chcete řídit, jak je uživateli upozornění, když objektu se změnil. Příklady kódu, které ukazují, jak implementovat <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType>, najdete v článku `ControlCollection` třídy v ukázkové dynamické ovládací prvky aplikace Excel a ukázkové dynamické ovládací prvky aplikace Word v [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
## <a name="persisting-changes-to-cached-data-in-password-protected-documents"></a>Zachování změny Data uložená v mezipaměti v dokumentech chráněný heslem  
 Pokud jste do mezipaměti datové objekty v dokumentu, který je chráněný heslem, změny data uložená v mezipaměti nejsou uloženy. Přepsáním dvě metody můžete uložit změny do data uložená v mezipaměti. Přepsat tyto metody dočasně odebrat ochranu při ukládání dokumentu a poté znovu nastavte ochranu po uložení bylo dokončeno.  
  
 Další informace najdete v tématu [postup: Data do mezipaměti v dokumentu chráněná heslem](../vsto/how-to-cache-data-in-a-password-protected-document.md).  
  
## <a name="preventing-data-loss-when-adding-null-values-to-the-data-cache"></a>Prevence ztráty dat při přidávání hodnoty Null do mezipaměti dat  
 Při přidání objektů do mezipaměti dat, všech objektů v mezipaměti musí být inicializována tak, aby jinou hodnotu než**null** hodnotu předtím, než je dokument uložit a zavřít. Pokud má všechny objektu v mezipaměti **null** hodnoty, když je dokument uložit a zavřít, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] se automaticky odeberou všechny uložené v mezipaměti objektů z mezipaměti data.  
  
 Pokud přidáte objekt s **hodnotu null** hodnotu do mezipaměti dat pomocí <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut v době návrhu, můžete použít <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídě pro inicializaci data uložená v mezipaměti objektů před otevření dokumentu. To je užitečné, pokud chcete inicializovat data uložená v mezipaměti na serveru bez Word či Excel nainstalovaná, před otevření dokumentu koncového uživatele. Další informace najdete v tématu [přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: ukládat Data do mezipaměti pro použití v režimu Offline nebo na serveru](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [Postupy: zdroji dat v dokumentu systému Office mezipaměti prostřednictvím kódu programu](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)   
 [Postupy: mezipaměti Data v dokumentu chráněném heslem](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [Návod: Vytvoření hlavního podrobný vztah, který pomocí datové sady v mezipaměti](../vsto/walkthrough-creating-a-master-detail-relation-using-a-cached-dataset.md)  
  
  