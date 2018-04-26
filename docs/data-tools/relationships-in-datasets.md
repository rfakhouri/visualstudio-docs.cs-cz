---
title: DataRelation použít k vytvoření relace mezi datové sady
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vbData.Microsoft.VSDesigner.DataSource.DesignRelation
- vbdata.Microsoft.VSDesigner.DataSource.DesignRelation
helpviewer_keywords:
- relationships, about relationships
- datasets [Visual Basic], relationships
- relationships, datasets
ms.assetid: cfe274f0-71fe-40f6-994e-7c7f6273c9ba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b3b101d251167a646b66568f7aacc005d7c792d7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="create-relationships-between-datasets"></a>Vytvářet vztahy mezi datové sady
Datové sady, které obsahují související data tabulky, použijte <xref:System.Data.DataRelation> objekty představují vztah nadřazený podřízený mezi tabulkami a vrácení souvisejících záznamů od sebe navzájem. Přidání souvisejících tabulek do datové sady pomocí **Průvodce konfigurací zdroje dat**, nebo **návrháře Dataset**, vytvoří a nakonfiguruje <xref:System.Data.DataRelation> objekt pro vás.

<xref:System.Data.DataRelation> Objektu provádí dvě funkce:

-   Ji můžete zpřístupnit záznamy související na záznam, který pracujete. Pokud jste v záznamu nadřazené poskytuje podřízené záznamy (<xref:System.Data.DataRow.GetChildRows%2A>) a nadřazeného záznamu při práci s podřízeného záznamu (<xref:System.Data.DataRow.GetParentRow%2A>).

-   Ho můžete vynutit omezení referenční integrity, jako je například odstraňování souvisejících podřízených záznamů, pokud odstraníte záznam nadřazené.

Je důležité si uvědomit rozdíl mezi spojení na hodnotu true a funkce <xref:System.Data.DataRelation> objektu. Záznamy v spojení na hodnotu true, jsou převzaty z nadřazené a podřízené tabulky a zařadit do jedné, plochý záznamů. Při použití <xref:System.Data.DataRelation> objekt, je vytvořena bez nové sady záznamů. Místo toho DataRelation sleduje relace mezi tabulkami a udržuje nadřazené a podřízené záznamy synchronizované.

## <a name="datarelation-objects-and-constraints"></a>DataRelation – objekty a omezení
A <xref:System.Data.DataRelation> objekt se také používá k vytvoření a vynutit následující omezení:

-   Jedinečné omezení, což zaručuje, že sloupec v tabulce obsahuje žádné duplikáty.

-   Omezení cizího klíče, který můžete použít k udržování referenční integrity mezi nadřazenou a podřízenou tabulkou v datové sadě.

Omezení, které zadáte v <xref:System.Data.DataRelation> objekt jsou implementované automaticky vytvořením příslušné objekty nebo nastavení vlastností. Pokud vytvoříte omezení cizího klíče pomocí <xref:System.Data.DataRelation> objekt, instance <xref:System.Data.ForeignKeyConstraint> třídy jsou přidány do <xref:System.Data.DataRelation> objektu <xref:System.Data.DataRelation.ChildKeyConstraint%2A> vlastnost.

Jedinečné omezení je implementována buď jednoduše nastavením <xref:System.Data.DataColumn.Unique%2A> vlastnost sloupce dat na `true` nebo přidáním instanci <xref:System.Data.UniqueConstraint> třídy k <xref:System.Data.DataRelation> objektu <xref:System.Data.DataRelation.ParentKeyConstraint%2A> vlastnost. Informace o pozastavení omezení v datové sadě najdete v tématu [vypnutí omezení při naplňování datové sady](../data-tools/turn-off-constraints-while-filling-a-dataset.md).

### <a name="referential-integrity-rules"></a>Pravidla referenční integrity
Jako součást omezení cizího klíče můžete zadat referenční integrity pravidla, která se použijí na tři body:

-   Při aktualizaci na nadřazený záznam

-   Když je odstraněn na nadřazený záznam

-   Při změně přijetí nebo zamítnutí

Pravidla, které můžete použít jsou určené v <xref:System.Data.Rule> výčet a jsou uvedené v následující tabulce.

|Pravidlo omezení pro cizí klíč|Akce|
|----------------------------------|------------|
|<xref:System.Data.Rule.Cascade>|(Aktualizace nebo odstranění) provedené na nadřazený záznam také změny v souvisejících záznamů v podřízené tabulce.|
|<xref:System.Data.Rule.SetNull>|Podřízené záznamy se neodstraní, ale nastavení cizí klíče v podřízené záznamy <xref:System.DBNull>. S tímto nastavením může být ponecháno podřízené záznamy "osamocené položky" – to znamená, že mít žádný vztah k nadřazené záznamy. **Poznámka:** pomocí tohoto pravidla můžete mít za následek neplatná data v podřízené tabulce.|
|<xref:System.Data.Rule.SetDefault>|Cizí klíče v relaci podřízené záznamy je nastaven na výchozí hodnotu (podle sloupce <xref:System.Data.DataColumn.DefaultValue%2A> vlastnost).|
|<xref:System.Data.Rule.None>|Souvisejících podřízených záznamů je provedena žádná změna. S tímto nastavením může obsahovat podřízené záznamy odkazují na neplatný nadřazené záznamy.|

Další informace o aktualizacích v tabulkách datovou sadu, najdete v části [uložit data zpět do databáze](../data-tools/save-data-back-to-the-database.md).

### <a name="constraint-only-relations"></a>Pouze omezení vztahů
Při vytváření <xref:System.Data.DataRelation> objektu, máte možnost určení, že vztah lze použít pouze k vynucení omezení – to znamená, je také se nepoužijí pro přístup k související záznamy. Tuto možnost můžete použít ke generování datové sady se mírně efektivnější a který obsahuje metody méně než jeden pomocí funkce související s záznamy. Nebudete však moci související záznamy. Například pouze omezení vztah brání odstranění na nadřazený záznam, který má stále podřízené záznamy a podřízené záznamy nelze získat přístup prostřednictvím nadřazené.

## <a name="manually-creating-a-data-relation-in-the-dataset-designer"></a>Ruční vytvoření vztahu data v Návrháři Dataset
Při vytváření datových tabulek pomocí nástrojů návrhu data v sadě Visual Studio, jsou automaticky vytvářet relace, pokud ze zdroje dat se dají shromáždit informace. Pokud ručně přidáte tabulky dat z **datovou sadu** kartě **sada nástrojů**, možná budete muset ručně vytvořit relaci. Další informace o vytváření <xref:System.Data.DataRelation> prostřednictvím kódu programu, najdete v části objekty [přidání DataRelations](/dotnet/framework/data/adonet/dataset-datatable-dataview/adding-datarelations).

Relace mezi tabulkami dat zobrazí jako řádky v **návrháře Dataset**, s klíč a infinity glyf znázorňující jeden mnoho aspektů relace. Ve výchozím nastavení nezobrazí název relace na návrhovou plochu.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-create-a-relationship-between-two-data-tables"></a>Chcete-li vytvořit relaci mezi dvěma datovými tabulkami

1.  Otevřete datovou sadu v **návrháře Dataset**. Další informace najdete v tématu [návod: vytvoření datové sady v Návrháři Dataset](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Přetáhněte **vztah** objektu z **datovou sadu** nástrojů do podřízené tabulky dat v relaci.

     **Vztah** otevře se dialogové okno, vyplní **podřízenou tabulku** pole s tabulkou, kterou jste přetáhli **vztah** objektu do.

3.  Vyberte nadřazenou tabulku z **nadřazenou tabulkou** pole. Nadřazená tabulka obsahuje záznamy na straně "1" vztah jeden mnoho.

4.  Ověřte, zda je správný podřízené tabulky zobrazí v **podřízenou tabulku** pole. Podřízené tabulky obsahuje záznamy na straně "n" vztah jeden mnoho.

5.  Zadejte název vztahu v rámci **název** pole, nebo ponechte výchozí název podle vybrané tabulky. Toto je název skutečnou <xref:System.Data.DataRelation> objektu v kódu.

6.  Vyberte sloupce, které ke tabulky **klíč sloupce** a **sloupce cizího klíče** uvádí.

7.  Vyberte, zda chcete vytvořit relace, omezení nebo obojí.

8.  Vyberte nebo zrušte **vnořené vztah** pole. Výběrem této možnosti se nastaví <xref:System.Data.DataRelation.Nested%2A> vlastnost, která má `true`, a způsobuje, že podřízená řádky vztah Nested v rámci nadřazeného sloupce, když jsou tyto řádky zapisují jako XML data nebo synchronizovány s <xref:System.Xml.XmlDataDocument>. Další informace najdete v tématu [vnoření DataRelations](/dotnet/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations).

9. Nastavte pravidla, která budou vynucena když děláte změny na záznamy v těchto tabulkách. Další informace naleznete v tématu <xref:System.Data.Rule>.

10. Klikněte na tlačítko **OK** k vytvoření vztahu. Vztah řádku se zobrazí v Návrháři mezi dvěma tabulkami.

#### <a name="to-display-a-relation-name-in-the-dataset-designer"></a>Chcete-li zobrazit název relace v Návrháři Dataset

1.  Otevřete datovou sadu v **návrháře Dataset**. Další informace najdete v tématu [návod: vytvoření datové sady v Návrháři Dataset](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Z **Data** nabídce vyberte možnost **zobrazení popisků relací** příkaz, který zobrazí název relace. Zrušte zaškrtnutí tohoto příkazu skrýt název relace.

## <a name="see-also"></a>Viz také

- [Vytvoření a konfigurace datových sad v sadě Visual Studio](../data-tools/create-and-configure-datasets-in-visual-studio.md)