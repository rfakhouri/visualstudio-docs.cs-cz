---
title: "Ladění textové šablony T4 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- text templates, troubleshooting
- text templates, debugging
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8408cfca0df02a903e4b6394e2b60dcffcfb2904
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="debugging-a-t4-text-template"></a>Ladění textové šablony T4
Nastavte zarážky v textové šablony. Chcete-li ladit návrhu textové šablony, uložte tento textový soubor šablony a poté zvolte **ladění šablony T4** v místní nabídce souboru v Průzkumníku řešení. Chcete-li ladit spuštění textové šablony, jednoduše ladění aplikace, do které patří.  
  
 K ladění textové šablony, byste měli porozumět kroky procesu transformace šablony. Různé druhy chyb, může dojít v jednotlivých kroků. Takto vypadají kroky.  
  
|Krok|Návrh šablony: když se stane|Spuštění šablony: když se stane|  
|----------|--------------------------------------------|-----------------------------------------|  
|Generování kódu z textové šablony.<br /><br /> Chyby v direktivy, nebo se nachází neodpovídající nebo disordered `<#...#>` značky.|Při uložení šablony nebo volání transformací textu.|Při uložení šablony nebo volání transformací textu.|  
|Kompilace generovaného kódu.<br /><br /> Chyby při kompilaci v kódu šablony.|Ihned po předchozím kroku.|Společně s kódu aplikace.|  
|Spustí kód.<br /><br /> Běhové chyby ve vašem kódu šablony.|Ihned po předchozím kroku.|Pokud je aplikace spuštěna a vyvolá kód šablony.|  
  
 Ve většině případů čísla řádků v kódu šablony jsou uvedeny v zprávy o chybách. Když zprávy o chybách odkazuje dočasný název souboru, obvykle příčinou je neshoda závorky v kódu textové šablony.  
  
 Můžete nastavit zarážky v textových šablonách a ladění obvyklým způsobem.  
  
## <a name="common-errors-and-fixes"></a>Běžné chyby a opravy  
 Následující tabulka uvádí nejběžnějších chyb a jejich opravy.  
  
|Chybová zpráva|Popis|Řešení|  
|-------------------|-----------------|--------------|  
|Nepodařilo se načíst základní třídu {0}' z které třídy transformace dědí.|Nastane, pokud nemůžete najít základní třída zadaná v `inherits` parametr – direktiva šablony. Zpráva poskytuje číslo – direktiva šablony.|Ujistěte se, že pro zadanou třídu existuje a že sestavení, které existuje ve je uveden v direktivu sestavení.|  
|Nepodařilo se vyřešit obsahují text pro file:{0}|Nastane, když nelze najít šablonu zahrnuty. Zpráva obsahuje název požadovaný soubor.|Ujistěte se, že cesta k souboru je relativní k cestě původní šablony, nebo, že soubor je v umístění, která je zaregistrovaná u hostitele nebo že je úplná cesta k souboru.|  
|Při inicializaci objektu transformace byly vygenerovány chyby. Transformace se nespustí.|Nastane, když 'Initialize()' třídy transformace se nezdařila nebo vrátí hodnotu false.|Kód ve funkci Initialize() pochází z transformace základní třída zadaná v \<#@template#> a z procesory direktiv. Chyba, která způsobila, že inicializovat selhání pravděpodobně je v seznamu chyb. Zjistěte, proč se nezdařilo. Pomocí následujících postupů k ladění šablonu můžete prohlédnout skutečné generovaný kód pro inicializace().|  
|Sestavení {0}' pro procesoru direktiv objekt {1}' nebyl udělen FullTrust sadou oprávnění. K poskytování procesory direktiv jsou povoleny pouze důvěryhodné sestavení. Tato procesoru direktiv se nenačte.|Nastane, když v systému nejsou udělena oprávnění FullTrust k sestavení obsahujícímu procesoru direktiv. Zpráva obsahuje název sestavení a název procesoru direktiv.|Ujistěte se, že používáte jenom důvěryhodné sestavení v místním počítači.|  
|Cesta {0}' musí být buď místní do tohoto počítače nebo jeho část vaší zóny důvěryhodných serverů.|Nastane, když direktiva nebo – direktiva assembly odkazuje na soubor, který není na místním počítači nebo na vaší síti zóny důvěryhodných serverů.|Se, zda adresář, kde se nachází – direktiva nebo sestavení direktivy ve vaší důvěryhodné zóně. Síťovému adresáři můžete přidat do zóny důvěryhodných prostřednictvím aplikace Internet Explorer.|  
|Více chyby syntaxe, jako je například "Neplatný token ' catch'" nebo "obor názvů nemůže přímo obsahovat členy"|Příliš mnoho uzavírací složené závorky v kódu šablony. Kompilátor je složitá ho pomocí standardní generování kódu.|Zkontrolujte číslo uzavření složené závorky a hranaté závorky v kódu oddělovače.|  
|Smyčky nebo podmíněné příkazy není zkompilovat nebo provést správně. Příklad: `<#if (i>10)#> Number is: <#= i #>`.<br /><br /> Tento kód vždy výstupy hodnotu i. Pouze "číslo:" je podmíněného.|V jazyce C# vždy pomocí složené závorky obklopit text bloků, které jsou součástí řídicí příkazy.|Přidat složené závorky: `<#if (i>10) { #>    Number is: <#= i #><# } #>`.|  
|"Příliš složitý výraz" při zpracování šablony návrhu nebo kompilování šablonu runtime (předběžně zpracované).<br /><br /> [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] přestane modul fungovat při pokusu o zkontrolovat kód vygenerovaný šablonu modulu runtime.|Blok textu je příliš dlouhý. T4 převede text bloky výraz zřetězení řetězce s jeden řetězcový literál pro každý řádek šablony. Bloky velmi dlouhý text můžete overstep kompilátoru omezení velikosti.|Rozdělte dlouhý text blok s bloku výraz například:<br /><br /> `<#= "" #>`|  
  
## <a name="warning-descriptions-and-fixes"></a>Popis upozornění a opravy  
 Následující tabulka uvádí nejběžnější upozornění společně s opravy, pokud je k dispozici.  
  
|Zpráva upozornění|Popis|Řešení|  
|---------------------|-----------------|--------------|  
|Načítání souboru zahrnout {0}' vrátila hodnotu null nebo prázdný řetězec.|V případě zahrnuté textového souboru šablony je prázdný. Zpráva obsahuje název souboru souboru zahrnuty.|Buď odeberte – direktiva include nebo zkontrolujte, zda že soubor má nějaký obsah.|  
|Kompilování transformace:|Přidá všechny chyby nebo upozornění při kompilaci transformace pocházející z kompilátoru tento řetězec. Tento řetězec znamená, že kompilátor došlo k chybě nebo upozornění.|Pokud máte potíže hledání knihovny DLL, musíte zadat úplnou cestu nebo plně kvalifikovaný silným názvem, pokud v mezipaměti GAC knihovnu DLL.|  
|Parametr {0}' již existuje v direktivu. Duplicitní parametr bude ignorován.|Nastane, když je parametr v direktivě zadán více než jednou. Zpráva poskytuje název parametru a číslo řádku direktivu.|Odeberte duplicitní parametr.|  
|Došlo k chybě při načítání souboru zahrnout: {0}. Direktiva include se budou ignorovat.|Nastane, když nelze najít soubor zadaný v `include` – direktiva. Zpráva obsahuje název souboru a číslo řádku direktivu.|Ujistěte se, zda že soubor existuje ve stejném adresáři jako soubor šablony původní text nebo v jednom z adresáře include, které jsou registrovány na hostiteli.|  
|Pro třídu transformace byla zadána neplatná základní třídy. Základní třída musí být odvozeny od Microsoft.VisualStudio.TextTemplating.TextTransformation.|Nastane při `inherits` parametr – direktiva šablony určuje třídu, která nedědí od `TextTransformation`. Zpráva poskytuje číslo – direktiva šablony.|Zadejte třídu odvozenou od `TextTransformation`.|  
|V – direktiva 'šablony' byla zadána neplatná jazykovou verzi. Jazyková verze musí být ve formátu "xx-XX". Bude použit neutrální jazykovou verzi.|Nastane, když je nesprávně zadán parametr jazykové verze v – direktiva šablony. Zpráva poskytuje číslo – direktiva šablony.|Změňte parametr jazykové verze platná jazyková verze ve formátu "xx-XX".|  
|Hodnotu neplatný ladění: {0} zadaná ve – direktiva šablony. Ladění hodnota musí být "true" nebo "Nepravda". Použije se výchozí hodnotu "false".|Nastane při `debug` je nesprávně zadán parametr – direktiva šablony. Zpráva poskytuje číslo – direktiva šablony.|Nastavte parametr ladění na "true" nebo "Nepravda".|  
|V – direktiva šablony byla zadána neplatná hodnota HostSpecific: {0}. Hodnota HostSpecific musí být "true" nebo "Nepravda". Použije se výchozí hodnotu "false".|Nastane při parametr specifický pro hostitele v `template` – direktiva je nesprávně zadán. Zpráva poskytuje číslo – direktiva šablony.|Nastavte parametr specifický pro hostitele na "true" nebo "Nepravda".|  
|Neplatný jazyk: {0} zadaná ve – direktiva 'šablony'. Jazyk musí být buď "C" nebo "VB". Použije se výchozí hodnota "C".|Nastane, když je zadán nepodporovaný jazyk v `template` – direktiva. Pouze "C" nebo "VB" jsou povoleny (rozlišování malých a velkých písmen). Zpráva poskytuje číslo – direktiva šablony.|Nastavte `language` parametr – direktiva šablony "C" nebo "VB".|  
|Více direktivy výstupu nebyly nalezeny v šabloně. Jenom první z nich se budou ignorovat.|Nastane při více `output` direktivy jsou určené v souboru šablony. Zpráva poskytuje číslo duplicitní výstupní direktivu.|Odeberte duplicitní `output` direktivy.|  
|Více direktivy šablon nebyly nalezeny v šabloně. Jenom první z nich se budou ignorovat. V rámci direktiva jedna šablona by měla zadat více parametrů pro – direktiva šablony.|Nastane, pokud zadáte více `template` direktivy v rámci textu souboru šablony (včetně zahrnuté soubory). Zpráva poskytuje číslo – direktiva duplicitní šablony.|Agregace různými `template` direktivy do jednoho `template` – direktiva.|  
|Pro direktivu s názvem: {0} byl zadán žádný procesoru. Direktiva budou ignorovány.|V případě zadáte `custom` – direktiva, ale nezadáte `processor` atribut. Zpráva obsahuje název direktiva a číslo řádku.|Zadejte `processor` atribut s názvem `directive` procesoru pro direktivu.|  
|Direktiva s názvem objekt {1}' nebyla nalezena procesor s názvem: {0}. Direktiva budou ignorovány.|Nastane, když systém nemůže najít `directive` procesoru, které jste zadali v rámci `custom` – direktiva. Zpráva poskytuje direktivy název, procesor název a číslo řádku direktivu.|Nastavte `processor` atribut v direktivě k názvu direktivy procesoru.|  
|Nebyl nalezen požadovaný parametr {0}' pro direktivu objekt {1}. Direktiva budou ignorovány.|Nastane, když systém neposkytuje požadovaný parametr direktivy. Zpráva obsahuje název chybějící parametr, direktivy název a číslo řádku.|Zadejte parametr chybí.|  
|Procesor s názvem: {0} nepodporuje direktiva s názvem objekt {1}. Direktiva budou ignorovány.|Nastane, když procesoru direktiv nepodporuje direktivu. Zpráva obsahuje název a řádek počtu problematické – direktiva společně s názvem direktivy procesoru.|Opravte název direktivu.|  
|Direktiva include pro soubor: {0} způsobí, že nekonečné smyčce.|Zobrazí v případě, že direktivy začlenění na kruhový zadávají (například soubor A obsahuje soubor B, který obsahuje soubor A).|Nezadávejte žádné cyklické direktivy začlenění.|  
|Spuštění transformace:|Přidá všechny chyby nebo upozornění, které jsou generovány při spuštění pro transformaci tento řetězec.|Nelze použít.|  
|Počáteční nebo koncový byl nalezen neočekávaný v rámci bloku. Ujistěte se, že nebylo nemá zadáno počáteční nebo koncové značky a zda neobsahuje žádné vnořené bloky v šabloně.|Zobrazí, když máte neočekávanou \<# nebo #>. To znamená pokud máte \<# po jiné otevřete značky, který ještě nebyl uzavřen, nebo můžete mít #> Pokud není žádná uzavřené otevřete značka před ním. Zpráva poskytuje číslo řádku neodpovídající značky.|Buď odeberte neodpovídající počáteční nebo koncové značky, nebo použijte řídicí znak.|  
|Direktivu byl zadán nesprávný formát. Direktiva budou ignorovány. Zadejte prosím direktiva ve formátu`<#@ name [parametername="parametervalue"]*  #>`|Zobrazit analyzátorem, pokud není zadán direktivu ve správném formátu. Zpráva poskytuje číslo nesprávné direktivu.|Ujistěte se, všechna direktivy jsou ve tvaru `<#@ name [parametername="parametervalue"]*  #>`. Další informace najdete v tématu [direktivy textových šablon T4](../modeling/t4-text-template-directives.md).|  
|Nepodařilo se načíst sestavení '{0}' pro registrované procesoru direktiv objekt {1}.<br /><br /> {2}|Nastane, když procesoru direktiv nebylo možné načíst pro hostitele. Zpráva identifikuje sestavení, zadaná pro procesoru direktiv a název procesoru direktiv.|Ujistěte se, že je procesoru direktiv správně zaregistrován a zda existuje sestavení.|  
|Nepodařilo se najít typ {0}' v sestavení objekt {1}' pro registrované procesoru direktiv '{2}.<br /><br /> {3}|Nastane, když typ procesoru direktiv nelze načíst z jeho sestavení. Zpráva obsahuje název typu, sestavení a procesoru direktiv.|Vshost vyhledá procesoru direktiv informace (název, sestavení a typ) v registru. Ujistěte se, že je procesoru direktiv správně zaregistrován a zda typ existuje v sestavení.|  
|Došlo k potížím při načítání sestavení {0}.|Nastane, když dojde k potížím při načítání sestavení. Zpráva obsahuje název sestavení.|Můžete zadat sestavení, které mají být načtena v \<@# assembly #> direktivy a procesory direktiv. Chybová zpráva, která následuje tento řetězec by měl poskytovat více dat na proč načtení sestavení se nezdařilo.|  
|Došlo k potížím, vytváření a inicializace procesoru pro direktivu s názvem objekt {1}. Typ procesoru je {0}. Direktiva budou ignorovány.|Nastane, když systém nemohl vytvořit nebo inicializovat direktivy procesor. Zpráva obsahuje název a řádek číslo směrnice a typ procesoru.|Ujistěte se, že používáte správné procesoru direktiv, a že procesoru direktiv veřejný výchozí konstruktor. Jinak použijte možnosti ladění a zjistěte, proč se nedaří metodu Initialize() direktivy procesoru. Další informace najdete v tématu [řešení potíží s textové šablony](../modeling/debugging-a-t4-text-template.md).|  
|Došlo k výjimce během zpracování direktivu s názvem: {0}.|Nastane, když procesoru direktiv vyvolá výjimku při zpracování direktivu.|Ujistěte se, zda jsou parametry, které chcete procesoru direktiv správné.|  
|Hostiteli došlo k výjimce při pokusu o překlad odkaz na sestavení: {0}.|Nastane, když hostitel vyvolá výjimku při pokusu o překlad odkaz na sestavení. Zpráva obsahuje sestavení odkazovat na řetězec.|Sestavení odkazy pocházet z \<@# assembly #> direktivy a z procesory direktiv. Ujistěte se, zda je správný parametr "název" zadané v parametru sestavení.|  
|Pokus o zadejte hodnotu nepodporované {1} {0}' pro direktivu {2}|Probíhá ve RequiresProvidesDirectiveProcessor (všechny naše generovaného procesory direktiv odvozena z něj), když zadáte nepodporované vyžaduje nebo poskytuje argument.|Ujistěte se, že názvy v name = "value, párů uvedených ve vyžaduje a poskytuje parametry jsou správné.|