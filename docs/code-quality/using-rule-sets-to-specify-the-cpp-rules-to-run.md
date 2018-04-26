---
title: Použití sad pravidel k určování pravidel C++ pro spuštění
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 571d54bb6bdf3673da8e40d6075c5b961d248fe5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="use-rule-sets-to-specify-the-c-rules-to-run"></a>Použití sad pravidel k určování pravidel C++ pro spuštění

V sadě Visual Studio, můžete vytvořit a upravit vlastní *sadu pravidel* podle potřeb konkrétní projekt přidružené analýza kódu. Chcete-li vytvořit vlastní pravidlo C++ nastaven, projekt C/C++ musí být otevřený v prostředí Visual Studio IDE. Otevřete sadu standardních pravidel v nástroji editor sad pravidel a pak přidejte nebo odebrání specifická pravidla a volitelně změňte akci, která nastane, když analýza kódu určuje, že došlo k porušení pravidlo.

Chcete-li vytvořit nové vlastní pravidlo nastavte, ukládáte ji pomocí nový název souboru. Sadu vlastních pravidel se automaticky přiřadí do projektu.

## <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Chcete-li vytvořit vlastní pravidlo z jednoho existující sady pravidel

1. V Průzkumníku řešení otevřete místní nabídky projektu a zvolte **vlastnosti**.

2. Na **vlastnosti** , zvolte **analýza kódu**.

3. V **pravidlo nastavené** rozevíracího seznamu, proveďte jednu z následujících akcí:

    - Vyberte sadu pravidel, který chcete přizpůsobit.

     \- nebo –

    - Zvolte  **\<Procházet... >** k určení nastavení existující pravidlo, které se nenachází v seznamu.

4. Zvolte **otevřete** zobrazíte pravidla v editoru sadu pravidel.

## <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Chcete-li upravit pravidlo nastavte v editoru sadu pravidel

- Chcete změnit zobrazovaný název sadu pravidel, na **zobrazení** nabídce zvolte **vlastnosti – okno**. Zadejte zobrazovaný název v **název** pole. Všimněte si, že zobrazovaný název se může lišit od názvu souboru.

- Pokud chcete přidat do vlastní sady pravidel všechna pravidla skupiny, zaškrtněte políčko skupiny. Chcete-li odebrat všechna pravidla skupiny, zrušte zaškrtnutí políčka.

- Chcete-li přidat konkrétní pravidlo do sady vlastní pravidlo, zaškrtněte políčko pravidla. Chcete-li odebrat pravidlo ze sady pravidel, zrušte zaškrtnutí políčka.

- Chcete-li změnit akce při porušení pravidlo v analýza kódu, zvolte **akce** pole pro pravidlo a pak vyberte jednu z následujících hodnot:

     **Upozornit** – vygeneruje upozornění.

     **Chyba** -, vygeneruje se chyba.

     **Žádný** – zakáže pravidlo. Tato akce je stejná jako odebrání pravidlo ze sady pravidel.

## <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Chcete-li skupinu, filtrovat nebo změňte pole v editoru sadu pravidla pomocí pravidla nastavte panelu nástrojů editoru

- Rozšířit pravidla ve všech skupinách, zvolte **Rozbalit vše**.

- Sbalit pravidla ve všech skupinách, zvolte **sbalit všechny**.

- Chcete-li změnit pravidla se seskupují podle pole, zvolte pole z **Group By** seznamu. Chcete-li zobrazit pravidla neseskupení, zvolte  **\<žádné >**.

- Chcete-li přidat nebo odebrat pole ve sloupcích pravidlo, zvolte **sloupec možnosti**.

- Chcete-li skrýt pravidla, která se nevztahují k aktuálnímu řešení, zvolte **skrýt pravidla, která se nevztahují k aktuálnímu řešení**.

- Chcete-li přepnout mezi zobrazení a skrytí pravidla, které jsou přiřazeny akce chyby, zvolte **zobrazit pravidla, která může způsobit chyby analýzy kódu**.

- Pro přepínání zobrazení a skrytí pravidla, které jsou přiřazeny akce upozornění, vyberte **zobrazit pravidla, která může generovat upozornění analýzy kódu**.

- Pro přepínání zobrazení a skrytí pravidla, které jsou přiřazeny **žádné** akce, zvolte **zobrazit pravidla, která nejsou povolené**.

- Chcete-li přidat nebo odebrat Microsoft výchozí pravidlo nastaví aktuální sady pravidel, zvolte **přidat nebo odebrat sady pravidel podřízené**.