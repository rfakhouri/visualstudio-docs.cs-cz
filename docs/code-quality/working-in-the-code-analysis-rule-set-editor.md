---
title: "Práce v pravidel nástroje Analýza kódu s editorem sad | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.ruleseteditor
ms.assetid: 370c97bf-bb29-4b2f-b9ae-ba125bce7b2d
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d5a0fc10230c4c2b7638e1be75770872e0dcf4aa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="working-in-the-code-analysis-rule-set-editor"></a>Práce s Editorem sad pravidel nástroje Analýza kódu
Editor sad pravidel analýzy kódu umožňuje určit pravidla, které jsou součástí vlastní sady pravidel a určit akci. Můžete také zadat akce, které se má provést při porušení pravidlo zaznamená analýza kódu.  
  
|Akce|Popis|  
|------------|-----------------|  
|**Upozornění**|Generuje upozornění v **seznam chyb** okno.|  
|**Chyba**|Vygeneruje chybu v **seznam chyb** okno.|  
|**None**|Zakáže pravidlo.|  
  
 Editor zobrazí pravidla ve stromové struktuře, která skupiny pravidla pomocí pravidla nastavit pole, které zadáte. Chcete-li přidat nebo odebrat pravidla sadu pravidel, proveďte jednu nebo více z následujících kroků:  
  
-   Vyberte nebo zrušte zaškrtnutí políček u uzlu skupiny přidat nebo odebrat všechna pravidla ve skupině. Když vyberete skupinu, všechna pravidla jsou nastaveny na **upozornění** akce.  
  
-   Klikněte **akce** pole skupiny a pak zadejte akce, která platí pro všechna pravidla ve skupině.  
  
-   Vyberte nebo zrušte zaškrtnutí políčka jednotlivých pravidel. Při zaškrtnutí políčka pro pravidlo vyberete, je pravidlo nastavené na akci upozornění.  
  
## <a name="rule-set-editor-toolbar"></a>Editor panelu nástrojů sady pravidel  
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
  
## <a name="rule-set-fields"></a>Sada polích pro pravidlo  
 Pravidlo nastavené pole zobrazované informace o pravidle nastavit a lze řadit a seskupovat seznamu pravidel. Chcete-li zobrazit nebo skrýt pole, klikněte na tlačítko **možnosti sloupec** v pravidle nastavit panelu nástrojů editoru a potom zkontrolujte nebo zrušte zaškrtnutí políčka polí k zobrazení nebo skrytí.  
  
 Následující tabulka popisuje pole sadu pravidel.  
  
|Pole|Popis|  
|-----------|-----------------|  
|**ID**|Identifikátor pravidla.|  
|**Kategorie**|Kromě jejich členství v sadách pravidel jsou také pravidel analýzy kódu seskupené podle kategorie. Další informace najdete v tématu [analýzy kódu pro spravovaný kód upozornění](../code-quality/code-analysis-for-managed-code-warnings.md).|  
|**Jméno**|Název pravidla.|  
|**Namespace**|Obor názvů pravidla.|  
|**Cílový typ**|Určuje, zda pravidlo je pro nativní, spravovat nebo databáze kódu.|  
|**Akce**|Akce prováděné při porušení pravidlo analýzou kódu spustit.<br /><br /> **Upozornění** – vygeneruje upozornění.<br /><br /> **Chyba** -, vygeneruje se chyba.<br /><br /> **Žádný** – zakáže pravidlo.<br /><br /> Můžete upravit pole akce. Nastavení hodnoty na hodnotu None je stejný jako zrušením zaškrtnutí políčka pro pravidlo.|  
|**Zdrojové sady pravidel**|Sada pravidel, který obsahuje pravidlo.|  
  
## <a name="sorting-and-filtering-rule-sets"></a>Řazení a filtrování sady pravidel  
 Ze záhlaví sloupců mřížky sadu pravidel můžete řadit a filtrovat podle hodnoty pole pravidla.  
  
-   Seřadit seznamy sadu pravidel, klikněte na záhlaví sloupce pole, podle kterého chcete seřadit. Pokud jsou seskupeny sady pravidel, je řazen jednotlivě každou skupinu.  
  
-   Chcete-li filtrovat podle hodnoty pole sady pravidel, klikněte na tlačítko filtru na záhlaví sloupce pole, podle kterého chcete filtrovat. Zaškrtněte políčka hodnoty, které chcete zobrazit a zrušte zaškrtnutí políčka hodnoty, které chcete skrýt.