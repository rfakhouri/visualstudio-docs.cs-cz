---
title: Metody DataContext (Návrhář O-R)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c149f4e5-3b61-4c33-892e-3e26d47f3eeb
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 4f3cd7db587c940b4d310f6354f83983aae659fb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="datacontext-methods-or-designer"></a>Metody DataContext (Návrhář relací objektů)

<xref:System.Data.Linq.DataContext> metody (v kontextu [technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)) jsou metody <xref:System.Data.Linq.DataContext> třídu, která spuštění uložené procedury a funkce v databázi.

<xref:System.Data.Linq.DataContext> Třída je [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třídu, která funguje jako kanál mezi databázi systému SQL Server a [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] tříd entit, které jsou namapované na databázi. <xref:System.Data.Linq.DataContext> Třída obsahuje metody pro připojení k databázi a manipulace s daty v databázi a informace o připojovacím řetězci. Ve výchozím nastavení <xref:System.Data.Linq.DataContext> třída obsahuje několik metod, které bude možné volat, například <xref:System.Data.Linq.DataContext.SubmitChanges%2A> metoda, která odesílá aktualizovaná data z [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třídy do databáze. Můžete také vytvořit další <xref:System.Data.Linq.DataContext> metody, které jsou mapovány na uložené procedury a funkce. Jinými slovy, při volání těchto vlastních metod spustí uložená procedura nebo funkce v databázi, <xref:System.Data.Linq.DataContext> metoda je namapována na. Můžete přidat nové metody <xref:System.Data.Linq.DataContext> třídy stejně, jako by přidejte metody rozšíření všechny třídy. Ale v diskusích o <xref:System.Data.Linq.DataContext> metody v kontextu [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], je <xref:System.Data.Linq.DataContext> metody, které jsou mapovány na uložené procedury a funkce, které jsou právě popsané.

## <a name="methods-pane"></a>Podokno metody

<xref:System.Data.Linq.DataContext> metody, které jsou mapovány na uložené procedury a funkce se zobrazují v podokně metody [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. V podokně metody je v podokně společně na straně **entity** podokně (hlavní návrhové ploše). Podokno metody obsahuje seznam všech <xref:System.Data.Linq.DataContext> metody, které jste vytvořili pomocí [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Ve výchozím nastavení v podokně metody je prázdný; Přetáhněte uložené procedury nebo funkce z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] k vytvoření <xref:System.Data.Linq.DataContext> metody a naplnit podokně metody. Další informace najdete v tématu [postupy: vytvoření DataContext metody namapované na uložené procedury a funkce (Návrhář relací objektů)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md).

> [!NOTE]
> Otevřete a zavřete podokno metody kliknutím pravým tlačítkem myši [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] a pak levým na **skrýt podokno metody** nebo **zobrazit podokno metody**, nebo použijte klávesovou zkratku CTRL + 1.

## <a name="two-types-of-datacontext-methods"></a>Dva typy metod DataContext

DataContext metody jsou tyto metody, které jsou mapovány na uložené procedury a funkce v databázi. Můžete vytvořit a přidat DataContext metody v podokně metody [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Existují dva odlišné typy <xref:System.Data.Linq.DataContext> metody; ty, které vrátí jednu nebo více sad výsledků dotazu a ty, které nepodporují:

-   <xref:System.Data.Linq.DataContext> metody, které vrací jeden nebo více sad výsledků dotazu:

     Tento druh vytvořit <xref:System.Data.Linq.DataContext> metoda když aplikaci právě potřebuje ke spuštění uložené procedury a funkce v databázi a vrátí výsledky. Další informace najdete v tématu [postupy: vytvoření DataContext metody namapované na uložené procedury a funkce (Návrhář relací objektů)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md), System.Data.Linq.ISingleResult\<T >, a <xref:System.Data.Linq.IMultipleResults>.

-   <xref:System.Data.Linq.DataContext> metody, které nevracejí sad výsledků dotazu: například vložení, aktualizace a odstraní pro třídu konkrétní entity.

     Tento druh vytvořit <xref:System.Data.Linq.DataContext> v případě, že aplikace má ke spuštění uložené procedury místo použití výchozí [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] změnit chování pro ukládání dat mezi třídu entity a databáze. Další informace najdete v tématu [postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="return-types-of-datacontext-methods"></a>Návratové typy metod DataContext

Při přetažení uložené procedury a funkce z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], návratový typ vygenerovaného <xref:System.Data.Linq.DataContext> metoda se liší v závislosti na tom, kde vyřadit položky. Odstranit položky přímo do existující třídy entity vytvoří <xref:System.Data.Linq.DataContext> metoda s návratovým typem třídy entity; odebrání položek na prázdnou oblast [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] (v obou podokno) vytvoří <xref:System.Data.Linq.DataContext> metodu, která vrátí automaticky generovaný typu. Automaticky generovaný typ, který je vytvořen má název, který odpovídá uloženou proceduru nebo název funkce a vlastnosti, které mapují na pole vrácené uložená procedura nebo funkce.

> [!NOTE]
> Můžete změnit návratový typ <xref:System.Data.Linq.DataContext> metoda po přidání do podokna metody. Zkontrolovat nebo změnit návratový typ <xref:System.Data.Linq.DataContext> metoda, vyberte ho a zkontrolujte **návratového typu** vlastnost **vlastnosti** okno. Další informace najdete v tématu [postupy: Změna návratový typ metody DataContext (Návrhář relací objektů)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

Objekty, které přetažení z databáze na plochu Návrhář relací objektů bude název automaticky na základě názvu objekty v databázi. Přetažením na stejný objekt více než jednou, připojí se ke konci nový název, který se odlišuje názvy číslo. Při názvy objektů databáze obsahovat mezery nebo znaky není podporované v jazyce Visual Basic nebo C#, místo nebo neplatný znak nahrazena podtržítkem.

## <a name="see-also"></a>Viz také

- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Uložené procedury](/dotnet/framework/data/adonet/sql/linq/stored-procedures)
- [Postupy: vytvoření metody DataContext namapované na uložené procedury a funkce (Návrhář relací objektů)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)
- [Postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [Návod: Přizpůsobení vložit, aktualizovat a odstraňovat chování tříd entit](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)
- [Návod: Vytváření třídy LINQ to SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)