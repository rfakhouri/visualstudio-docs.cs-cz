---
title: Přístup k datům v dokumentech na serveru
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], accessing on server
- data access [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b6203282404f6dc01f51f7cea68f90fa7a759c56
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="accessing-data-in-documents-on-the-server"></a>Přístup k datům v dokumentech na serveru
  Můžete ovládat data v přizpůsobení na úrovni dokumentu bez nutnosti použít objektový model Microsoft Office Word nebo Microsoft Office Excel. To znamená, že můžete přístup k datům obsaženým v dokumentu na serveru, který nemá slovo nebo nainstalovat aplikace Excel. Například kód na serveru (například v [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] stránky) můžete upravit data v dokumentu a odeslání přizpůsobených dokumentu pro koncového uživatele. Když se koncový uživatel otevře dokument, kód vazby dat v sestavení řešení váže vlastních dat do dokumentu. To je možné, protože data v dokumentu je oddělená od uživatelského rozhraní. Další informace najdete v tématu [Data do mezipaměti v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md).  

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  

## <a name="caching-data-for-use-on-a-server"></a>Ukládání dat do mezipaměti pro použití na serveru  
 Pro ukládání do mezipaměti objekt dat v dokumentu, označte ji s <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut v době návrhu, nebo pomocí `StartCaching` metoda hostitele položky v době běhu. Když mezipaměti objekt dat v dokumentu, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] serializuje objekt do formátu řetězce XML, který je uložený v dokumentu. Objekty musí splňovat určité požadavky způsobilé k ukládání do mezipaměti. Další informace najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md).  

 Kódu na straně serveru můžete upravit všechny objekty dat v datové mezipaměti. Ovládací prvky vázané na data uložená v mezipaměti instance jsou synchronizovány s uživatelským rozhraním, tak, aby všechny změny na straně serveru, které jsou vytvářeny pro data zobrazí automaticky při otevření dokumentu na straně klienta.  

## <a name="accessing-data-in-the-cache"></a>Přístup k datům v mezipaměti  
 Data v mezipaměti můžete přistupovat z aplikace mimo Office, třeba z konzolové aplikace, aplikace Windows Forms nebo na webové stránce. Aplikace, který přistupuje k data uložená v mezipaměti musí mít úplný vztah důvěryhodnosti; Webové aplikace s částečnou důvěryhodností nelze vložit, načíst nebo změnit data, která se uloží do mezipaměti v dokumentu systému Office.  

 Data mezipaměť je přístupná prostřednictvím hierarchie kolekce, které jsou vystavené <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> vlastnost <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třídy:  

-   <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> Vlastnost vrátí <xref:Microsoft.VisualStudio.Tools.Applications.CachedData>, která obsahuje všechna data uložená v mezipaměti v přizpůsobení na úrovni dokumentu.  

-   Každý <xref:Microsoft.VisualStudio.Tools.Applications.CachedData> obsahuje jeden nebo více <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> objekty. A <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> obsahuje všechna data uložená v mezipaměti objektů, které jsou definované v rámci jedné třídy.  

-   Každý <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> obsahuje jeden nebo více <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> objekty. A <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> představuje objekt jednoho data uložená v mezipaměti.  

 Následující příklad kódu ukazuje, jak pro přístup k řetězec uložený v mezipaměti v `Sheet1` třída projektu sešitu aplikace Excel. Tato ukázka je součástí většího příkladu vztahujícího se k <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> metoda.  

 [!code-csharp[Trin_ServerDocument#12](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#12)]
 [!code-vb[Trin_ServerDocument#12](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#12)]  

## <a name="modifying-data-in-the-cache"></a>Úprava dat v mezipaměti  
 Pokud chcete upravit objekt data uložená v mezipaměti, je obvykle provést následující kroky:  

1.  Deserializuje reprezentaci XML objektu v mezipaměti do nové instance objektu. Máte přístup k souboru XML pomocí <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> vlastnost <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> představující objekt data uložená v mezipaměti.  

2.  Proveďte změny této kopie.  

3.  Serializujte objekt změněné zpět do mezipaměti data pomocí jedné z následujících možností:  

    -   Pokud chcete automaticky serializovat změny, použijte <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> metoda. Tato metoda používá **formát DiffGram** formát pro serializaci <xref:System.Data.DataSet>, <xref:System.Data.DataTable>a typové datové sady objektů v datové mezipaměti. **Formát DiffGram** formát zajišťuje, že změny v datové mezipaměti v režimu offline dokumentu jsou správně odeslány na server.  

    -   Pokud chcete provést vlastní serializace pro změny data uložená v mezipaměti, můžete psát přímo na <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> vlastnost. Zadejte **formát DiffGram** formátu, pokud používáte <xref:System.Data.Common.DataAdapter> aktualizace databáze se změny dat v <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, nebo typové datové sady. Jinak <xref:System.Data.Common.DataAdapter> zaktualizuje databázi přidáním nové řádky místo úpravy existujících řádků.  

### <a name="modifying-data-without-deserializing-the-current-value"></a>Úprava dat bez deserializaci aktuální hodnota  
 V některých případech můžete chtít změnit hodnotu objektu v mezipaměti bez první deserializaci aktuální hodnotu. Například musíte Pokud chcete změnit hodnotu objektu, který má na jednoduchý typ, třeba řetězec nebo celé číslo, nebo pokud se inicializace uložené v mezipaměti <xref:System.Data.DataSet> v dokumentu na serveru. V těchto případech můžete použít <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> metoda bez první deserializaci aktuální hodnota objektu v mezipaměti.  

 Následující příklad kódu ukazuje, jak změnit hodnotu řetězec uložený v mezipaměti v `Sheet1` třída projektu sešitu aplikace Excel. Tato ukázka je součástí většího příkladu vztahujícího se k <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> metoda.  

 [!code-csharp[Trin_ServerDocument#11](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#11)]
 [!code-vb[Trin_ServerDocument#11](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#11)]  

### <a name="modifying-null-values-in-the-data-cache"></a>Úprava hodnoty Null v datové mezipaměti  
 Datové mezipaměti neukládá objekty, které mají hodnotu **null** když je dokument uložit a zavřít. Toto omezení má několik důsledky, když upravíte data uložená v mezipaměti:  

-   Pokud nastavíte všech objektů v datové mezipaměti na hodnotu **null**, všechny objekty v datové mezipaměti bude automaticky nastavena na **null** při otevření dokumentu a mezipaměti celý data budou vymazána při dokument je uložit a zavřít. To znamená, všechny objekty v mezipaměti se odeberou z mezipaměti dat a <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> kolekce bude prázdný.  

-   Pokud vytvoříte řešení s **null** objekty v datové mezipaměti a vy chcete inicializace tyto objekty pomocí <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> třída před dokumentu je otevřen poprvé, je třeba zkontrolovat všechny objekty inicializaci v datové mezipaměti. Pokud jste inicializovat pouze některé objekty, všechny objekty, je možnost **null** při otevření dokumentu a celou datovou mezipaměť budou vymazána, když je dokument uložit a zavřít.  

## <a name="accessing-typed-datasets-in-the-cache"></a>Přístup k typové datové sady v mezipaměti  
 Pokud chcete přístup k datům v typové datové sady z řešení Office a z aplikace mimo Office, jako je například aplikace Windows Forms nebo [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] projektu typové datové sady je nutné definovat v samostatném sestavení, který se odkazuje v obou projekty. Pokud přidáte typové datové sady pro každý projekt pomocí **Průvodce konfigurací zdroje dat** nebo **návrháře Dataset**, rozhraní .NET Framework bude považovat typové datové sady v dva projekty jako různé typy . Další informace o vytvoření typové datové sady, najdete v části [vytvořit a nakonfigurovat datové sady v sadě Visual Studio](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).  

## <a name="see-also"></a>Viz také  
 [Přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md)   
 [Data uložená v mezipaměti v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md)  
