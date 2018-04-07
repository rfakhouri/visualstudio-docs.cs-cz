---
title: Použití editorem sad pravidel nástroje Analýza kódu v sadě Visual Studio | Microsoft Docs
ms.date: 04/-4/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.ruleseteditor
ms.assetid: 370c97bf-bb29-4b2f-b9ae-ba125bce7b2d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c861a6beda6b0196ec03987915b1503f4cc55a19
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2018
---
# <a name="use-the-code-analysis-rule-set-editor"></a>Použití, které s editorem sad pravidel nástroje Analýza kódu

Sada editoru kódu analysis pravidlo umožňuje určit pravidla, které jsou součástí vlastní sady pravidel a závažnost porušení pravidel.

|Akce (závažnost)|Popis|
|-|-|
|Upozornění|Generuje upozornění v **seznam chyb** a také v čase vytvoření buildu.|
|Chyba|Vygeneruje chybu v **seznam chyb** a také v čase vytvoření buildu.|
|Informace o|Generuje zprávy v **seznam chyb**.|
|Hidden|Narušení není viditelné pro uživatele. Prostředí IDE, je upozornění narušení, ale.|
|Žádné|Pravidlo je potlačeno. Chování je stejné jako v případě, že pravidlo bylo odebráno ze sady pravidel.|

Editor zobrazí pravidla ve stromové struktuře, která skupiny pravidla pomocí pravidla nastavit pole, které zadáte. Chcete-li přidat nebo odebrat pravidla sadu pravidel, proveďte jednu nebo více z následujících kroků:

- Vyberte nebo zrušte zaškrtnutí políček u uzlu skupiny přidat nebo odebrat všechna pravidla ve skupině. Když vyberete skupinu, všechna pravidla jsou nastaveny na **upozornění** akce.

   > [!TIP]
   > Jak pravidla se seskupují v, můžete změnit **Seskupit podle** rozevíracího seznamu.

- Klikněte **akce** pole skupiny a pak zadejte akce, která platí pro všechna pravidla ve skupině.

- Vyberte nebo zrušte zaškrtnutí políčka jednotlivých pravidel. Při zaškrtnutí políčka pro pravidlo vyberete, je pravidlo nastavené na akci upozornění.

## <a name="toolbar"></a>Panel nástrojů

Můžete panelu nástrojů editoru sadu pravidlo skupiny, filtrovat a vyhledávat data, která se zobrazí v mřížce sadu pravidel.

Následující tabulka popisuje ovládacích prvků na panelu nástrojů editoru sadu pravidel.

|Toolbar – ovládací prvek|Popis|
|---------------------|-----------------|
|**Rozbalit vše**|Ukazuje pravidla ve všech skupinách.|
|**Sbalit vše**|Skryje pravidla ve všech skupinách.|
|**Seskupit podle**|Určuje pole pravidla se seskupují. Klikněte na tlačítko  **\<žádné >** zobrazíte pravidla bez skupiny.|
|**Možnosti sloupce**|Určuje pravidlo polí k zobrazení.|
|**Skrýt pravidla, která se nevztahují k aktuálnímu řešení**|Zobrazí nebo skryje pravidla, které nejsou stejného typu cíl jako řešení.|
|**Zobrazit pravidla, která může způsobit chyby analýzy kódu**|Zobrazí nebo skryje pravidla, které jsou přiřazeny akce chyby.|
|**Zobrazit pravidla, která může generovat upozornění analýzy kódu**|Zobrazí nebo skryje pravidla, které jsou přiřazeny akce upozornění.|
|**Zobrazit pravidla, která není povoleno**|Zobrazí nebo skryje pravidla, která jsou přiřazena žádná akce.|
|**Přidat nebo odebrat podřízené sady pravidel**|Přidá nebo odebere vybrané pravidlo sad pravidel.|
|**Vyhledat pravidla**|Vyhledá všechny hodnoty polí pro řetězec, který zadáte.|

## <a name="rule-set-fields"></a>Pole sady pravidel

Pravidlo sady polí zobrazení informací o sadu pravidel a lze řadit a seskupovat seznamu pravidel. Chcete-li zobrazit nebo skrýt polí, vyberte **možnosti sloupec** v pravidle nastavit panelu nástrojů editoru a pak zaškrtněte nebo zrušte zaškrtnutí zaškrtněte políčka pole, která chcete zobrazit nebo skrýt.

Následující tabulka popisuje pole sadu pravidel:

|Pole|Popis|
|-----------|-----------------|
|**ID**|Identifikátor pravidla.|
|**Kategorie**|Kromě jejich členství v sadách pravidel jsou také pravidel analýzy kódu seskupené podle kategorie. Další informace najdete v tématu [upozornění analýzy kódu](../code-quality/code-analysis-for-managed-code-warnings.md).|
|**Jméno**|Název pravidla.|
|**Namespace**|Obor názvů pravidla.|
|**Cílový typ**|Určuje, zda pravidlo je pro nativní, spravovat nebo databáze kódu.|
|**Akce**|Akce prováděné při porušení pravidlo analýzou kódu spustit. Můžete upravit **akce** pole.|
|**Zdrojové sady pravidel**|Sada pravidel, který obsahuje pravidlo.|

## <a name="sort-and-filter-rule-sets"></a>Třídění a filtrování sady pravidel

Ze záhlaví sloupců mřížky sadu pravidel můžete řadit a filtrovat podle hodnoty pole pravidla.

- Seřadit seznamy sadu pravidel, klikněte na záhlaví sloupce pole, podle kterého chcete seřadit. Pokud jsou seskupeny sady pravidel, je řazen jednotlivě každou skupinu.

- Chcete-li filtrovat podle hodnoty pole sady pravidel, klikněte na tlačítko filtru na záhlaví sloupce pole, podle kterého chcete filtrovat. Zaškrtněte políčka hodnoty, které chcete zobrazit a zrušte zaškrtnutí políčka hodnoty, které chcete skrýt.

## <a name="see-also"></a>Viz také

- [Vytvoření vlastní sady pravidel](../code-quality/how-to-create-a-custom-rule-set.md)