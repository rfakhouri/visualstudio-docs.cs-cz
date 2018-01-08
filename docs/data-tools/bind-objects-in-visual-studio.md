---
title: "Vazby objektů v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], object binding
- data [Visual Studio], binding to objects
- object binding
- binding, to objects
ms.assetid: ed743ce6-73af-45e5-a8ff-045eddaccc86
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 64031303545f293d9274158eeb1527ba26676751
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="bind-objects-in-visual-studio"></a>Vazby objektů v sadě Visual Studio
Visual Studio poskytuje nástroje pro návrh pro práci s vlastní objekty jako zdroj dat v aplikaci. Když chcete k ukládání dat z databáze v objektu, který vytvoření vazby ovládacích prvků uživatelského rozhraní, o doporučený postup je použití rozhraní Entity Framework pro generování třídu nebo třídy. Rozhraní Entity Framework automaticky generuje všechny standardní sledování změn kód, což znamená, že všechny změny na místní objekty jsou automaticky trvalé do databáze při jste DbSet objektu volejte metodu AcceptChanges. Další informace najdete v tématu [Entity Framework dokumentaci](https://ef.readthedocs.org/en/latest/).  
  
> [!TIP]
>  Přístupy k objektu vazby v tomto článku byste měli uvažovat pouze pokud je aplikace již založená na datové sady. Tato řešení můžete také použijí, pokud jste již obeznámeni s datovými sadami a data, která bude zpracovávat se tabulkové a příliš složitý nebo příliš velký. Příklad i jednodušší, zahrnující načítání dat přímo do objektů pomocí DataReader – a ručně aktualizace uživatelského rozhraní bez vazby dat, naleznete v části [vytvoření jednoduché datové aplikace pomocí ADO.NET](../data-tools/create-a-simple-data-application-by-using-adonet.md).  
  
## <a name="object-requirements"></a>Požadavky na objekt  
 Jediný požadavek pro vlastní objekty pro práci s daty nástrojů návrhu v sadě Visual Studio je, že objekt potřebuje aspoň jedna veřejná vlastnost.  
  
 Obecně platí vlastní objekty nevyžadují žádné konkrétní rozhraní, konstruktory nebo atributů tak, aby fungoval jako zdroj dat pro aplikaci. Ale pokud budete chtít přetáhněte objekt z **zdroje dat** okna návrhové ploše k vytvoření ovládacího prvku vázané na data, a pokud objekt implementuje <xref:System.ComponentModel.ITypedList> nebo <xref:System.ComponentModel.IListSource> rozhraní, objekt musí mít výchozí konstruktor. Jinak Visual Studio nelze doložit objekt zdroje dat a zobrazí chybu při přetažení položky na plochu návrháře.  
  
## <a name="examples-of-using-custom-objects-as-data-sources"></a>Příklady použití vlastních objektů jako zdroje dat  
 Při obrovském množství způsoby, jak implementovat aplikační logiku při práci s objekty jako zdroj dat se pro SQL databáze existuje jsou několik standardní operace, které můžete zjednodušit pomocí objektů TableAdapter generovaný Visual Studio. Tato stránka vysvětluje, jak implementovat tyto standardních procesů pomocí TableAdapters.It není určen jako vodítko k vytvoření vlastních objektů. Například obvykle provedete následující standardní operace bez ohledu na konkrétní implementaci vašich objektů nebo logiku aplikace:  
  
-   Načítání dat do objektů (většinou z databáze).  
  
-   Vytvoření typové kolekce objektů.  
  
-   Objekty, které se přidávání a odebírání objektů z kolekce.  
  
-   Zobrazení dat objektu pro uživatele ve formuláři.  
  
-   Změna nebo úpravy dat v objektu.  
  
-   Ukládání dat z objektů zpět do databáze.   
  
### <a name="load-data-into-objects"></a>Načíst data do objektů  
 V tomto příkladu je načíst data do vašich objektů pomocí TableAdapters. Ve výchozím nastavení TableAdapters vytvořené mají dva typy metod, které načíst data z databáze a naplnění datových tabulek.  
  
-   `TableAdapter.Fill` Metoda doplní existující data tabulky s daty vrácenými.  
  
-   `TableAdapter.GetData` Metoda vrátí novou tabulku dat naplněný daty.  
  
 Nejjednodušší způsob, jak načíst vaše vlastní objekty s daty je volat `TableAdapter.GetData` metoda, procházení kolekce řádků v tabulce vrácená data a naplňte každý objekt s hodnotami v jednotlivých řádcích. Můžete vytvořit `GetData` metoda, která vrací tabulku vyplněná data pro jakýkoli dotaz, přidat do TableAdapter.  
  
> [!NOTE]
>  Visual Studio názvy dotazů TableAdapter `Fill` a `GetData` ve výchozím nastavení, ale tyto názvy můžete změnit na libovolný platný název metody.  
  
 Následující příklad ukazuje, jak projít řádků v tabulce dat a naplnit objekt s daty:  
  
 [!code-csharp[VbRaddataConnecting#4](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_1.cs)]
 [!code-vb[VbRaddataConnecting#4](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_1.vb)]  
  
### <a name="create-a-typed-collection-of-objects"></a>Vytvoření typové kolekce objektů  
 Můžete vytvořit kolekce tříd pro objektů nebo použít typu kolekce, které jsou automaticky poskytované [BindingSource – komponenta](/dotnet/framework/winforms/controls/bindingsource-component).  
  
 Když vytváříte třídu vlastní kolekce pro objekty, doporučujeme dědění ze <xref:System.ComponentModel.BindingList%601>. Tato obecná třída poskytuje funkce pro správu kolekce, jakož i možnost vyvolávání událostí, které odesílat oznámení do infrastruktury datové vazby v systému Windows Forms.  
  
 Kolekce automaticky generovány v <xref:System.Windows.Forms.BindingSource> používá <xref:System.ComponentModel.BindingList%601> pro jeho typu kolekce. Pokud aplikace nevyžaduje žádný další funkce, pak je možné uchovávat v rámci vaší kolekce <xref:System.Windows.Forms.BindingSource>. Další informace najdete v tématu <xref:System.Windows.Forms.BindingSource.List%2A> vlastnost <xref:System.Windows.Forms.BindingSource> třídy.  
  
> [!NOTE]
>  Pokud vaše kolekce vyžaduje funkce není poskytovaný základní implementace <xref:System.ComponentModel.BindingList%601>, měli byste vytvořit vlastní kolekce, můžete přidat do třídy podle potřeby.  
  
 Následující kód ukazuje, jak vytvořit s třídou pro kolekci silného typu `Order` objekty:  
  
 [!code-csharp[VbRaddataConnecting#8](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_2.cs)]
 [!code-vb[VbRaddataConnecting#8](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_2.vb)]  
  
### <a name="add-objects-to-a-collection"></a>Přidat objekty do kolekce  
 Objekty lze přidávat do kolekce voláním `Add` metoda vaší třídy vlastní kolekce nebo <xref:System.Windows.Forms.BindingSource>.  
  
 
> [!NOTE]
>  `Add` Metoda automaticky zajištěna pro vlastní shromažďování při dědění ze <xref:System.ComponentModel.BindingList%601>.  
  
 Následující kód ukazuje, jak přidat objekty do typu kolekce v <xref:System.Windows.Forms.BindingSource>:  
  
 [!code-csharp[VbRaddataConnecting#5](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_3.cs)]
 [!code-vb[VbRaddataConnecting#5](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_3.vb)]  
  
 Následující kód ukazuje, jak přidat objekty do typu kolekce, která dědí z <xref:System.ComponentModel.BindingList%601>:  
  
> [!NOTE]
>  V tomto příkladu `Orders` kolekce je vlastnost `Customer` objektu.  
  
 [!code-csharp[VbRaddataConnecting#6](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_4.cs)]
 [!code-vb[VbRaddataConnecting#6](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_4.vb)]  
  
### <a name="remove-objects-from-a-collection"></a>Odeberte objekty z kolekce  
 Odeberte objekty z kolekce voláním `Remove` nebo `RemoveAt` metoda vaší třídy vlastní kolekce nebo <xref:System.Windows.Forms.BindingSource>.  
  
> [!NOTE]
>  `Remove` a `RemoveAt` metody automaticky dostupné pro vlastní shromažďování při dědění ze <xref:System.ComponentModel.BindingList%601>.  
  
 Následující kód ukazuje, jak vyhledat a odstranit objekty z typu kolekce <xref:System.Windows.Forms.BindingSource> s <xref:System.Windows.Forms.BindingSource.RemoveAt%2A> metoda:  
  
 [!code-csharp[VbRaddataConnecting#7](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_5.cs)]
 [!code-vb[VbRaddataConnecting#7](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_5.vb)]  
  
### <a name="display-object-data-to-users"></a>Má uživatelům zobrazit data objektu.  
 K zobrazení dat v objektech pro uživatele, vytvořit zdroj dat objekt pomocí **konfigurace zdroje dat** průvodce a poté přetáhněte jednotlivé vlastnosti nebo celý objekt do formuláře z **zdroje dat**okno.  
  
### <a name="modify-the-data-in-objects"></a>Změna dat v objekty  
 Chcete-li upravit data ve vlastních objektů, které jsou vázané na data pro ovládací prvky Windows Forms, jednoduše upravte data v připojeného ovládacího prvku (nebo přímo v vlastností objektu). Datová vazba architektura aktualizuje data v objektu.  
  
 Pokud vaše aplikace vyžaduje sledování změn a vrácení zadní navrhované změny na původní hodnoty, musí tuto funkci implementovat v objektovém modelu. Příklady jak tabulky dat udržování přehledu o navrhované změny, naleznete v tématu <xref:System.Data.DataRowState>, <xref:System.Data.DataSet.HasChanges%2A>, a <xref:System.Data.DataTable.GetChanges%2A>.  
  
### <a name="save-data-in-objects-back-to-the-database"></a>Uložení dat v objekty zpět do databáze  
 Uložte data zpět do databáze pomocí předání hodnoty z objektu TableAdapter DBDirect – metody.  
  
 Visual Studio vytvoří DBDirect metody, které mohou být provedeny přímo s databází. Tyto metody nevyžadují datové sady nebo DataTable objektů.  
  
|TableAdapter DBDirect – metoda|Popis|  
|----------------------------------|-----------------|  
|`TableAdapter.Insert`|Přidá nové záznamy do databáze, abyste mohli předat hodnoty jednotlivých sloupců jako parametry metody.|  
|`TableAdapter.Update`|Aktualizuje existující záznamy v databázi. Metoda aktualizace vezme hodnoty původní a nové sloupce jako parametry metody. Původní hodnoty, které se používají pro vyhledání původní záznam a s novými hodnotami, které se používají k aktualizaci záznamů.<br /><br /> `TableAdapter.Update` Metoda slouží také k sjednotit provedením změn v datové sadě zpět do databáze, <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow>, nebo pole <xref:System.Data.DataRow>s jako parametry metody.|  
|`TableAdapter.Delete`|Odstraní existující záznamy z databáze založené na původní hodnoty ve sloupcích předána jako parametry metody.|  
  
 Pokud chcete uložit data z kolekce objektů, projít kolekci objektů (například pomocí smyčky pro další). Odešlete hodnoty pro každý objekt do databáze pomocí TableAdapter DBDirect – metody.  
  
 Následující příklad ukazuje, jak používat `TableAdapter.Insert` DBDirect metoda pro přidání nového zákazníka přímo do databáze:  
  
 [!code-csharp[VbRaddataSaving#23](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_6.cs)]
 [!code-vb[VbRaddataSaving#23](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_6.vb)]  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)