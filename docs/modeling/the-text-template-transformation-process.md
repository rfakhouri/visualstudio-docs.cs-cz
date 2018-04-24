---
title: Proces transformace textových šablon
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, transformation process
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 322a8aac233f739180de903779210e1446306166
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="the-text-template-transformation-process"></a>Proces transformace textových šablon
Proces transformace textových šablon trvá textového souboru šablony jako vstup a generuje nový textový soubor jako výstup. Například textové šablony můžete použít ke generování kódu Visual Basic a C#, nebo můžete vygenerovat sestavu ve formátu HTML.

 Tři komponenty účasti v tomto procesu: modul, hostitele a procesory direktiv. Modul řídí proces; komunikuje se službou hostitel a procesoru direktiv k vytvoření výstupního souboru. Hostitel poskytuje interakce s prostředím, jako je hledání souborů a sestavení. Procesoru direktiv přidá funkce, jako je například čtení dat ze souboru XML nebo databáze.

 Proces transformace textových šablon se provádí ve dvou krocích. Modul nejprve vytvoří dočasné třída, která se označuje jako třídy generované transformace. Tato třída obsahuje kód, který je generován direktivy a řídicí bloky. Od tohoto modulu zkompiluje a provede třídy generované transformace k vytvoření výstupního souboru.

## <a name="components"></a>Součásti

|Součást|Popis|Přizpůsobitelné (Ano/Ne)|
|---------------|-----------------|------------------------------|
|Modul|Součásti modul řídí proces transformace textových šablon|Ne.|
|Hostitel|Hostitel je rozhraní mezi modul a uživatelského prostředí. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je hostitel proces transformace textových.|Ano. Můžete napsat vlastního hostitele.|
|Procesory direktiv|Procesory direktiv jsou třídy, které zpracovávají direktivy v textových šablonách. Direktivy slouží k poskytování dat textové šablony ze vstupního zdroje.|Ano. Můžete napsat vlastní procesory direktiv|

## <a name="the-engine"></a>Modul
 Modul přijímá šablony jako řetězec z hostitele, která zpracovává všechny soubory, které se používají v procesu transformace. Modul následně požádá na hostiteli a najít všechny vlastní procesory direktiv a dalších aspektů prostředí. Modul pak zkompiluje a spustí třídy generované transformace. Modul vrátí vygenerovaný text na hostitele, který obvykle text uloží do souboru.

## <a name="the-host"></a>Hostitele
 Hostitel je zodpovědná za všechno, co má vztah k prostředí mimo proces transformace, včetně následujících:

-   Hledání textu a binární soubory, které požadoval direktivy procesor nebo modul. Hostitel může hledat adresářů a globální mezipaměti sestavení najít sestavení. Hostitele lze najít vlastního procesoru direktiv kód pro modul. Hostitele lze také najít a čtení textových souborů a vrátí jejich obsah jako řetězce.

-   Poskytuje seznam standardní sestavení a obory názvů, které používá modul pro vytvoření třídy generované transformace.

-   Poskytování doméně aplikace, která se používá, když modul zkompiluje a provede třídy generované transformace. Samostatné doméně aplikace se používá pro účely ochranu před chybami v kódu šablony hostitelskou aplikaci.

-   Zapisování souboru generovaný výstup.

-   Nastavení výchozí rozšíření pro soubor generovaný výstup.

-   Zpracování chyb transformace text šablony. Například můžete hostitele zobrazit chyby v uživatelském rozhraní nebo jejich zápis do souboru. (V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], chyby se zobrazí v okně chybové zprávy.)

-   Poskytuje hodnotu povinný parametr, pokud uživatel má direktivu volána bez zadání hodnotu. Procesoru direktiv můžete zadat název direktiva a parametr a zeptejte se na hostiteli a poté zadejte výchozí hodnotu, pokud jej obsahuje.

## <a name="directives-and-directive-processors"></a>Direktivy a procesory direktiv
 Direktivu je příkaz v textové šablony. Poskytuje parametry pro proces generování. Obvykle direktivy zadejte zdroj a typ modelu nebo jiného vstupu a příponu názvu souboru výstupního souboru.

 Direktivy procesoru může zpracovat jeden nebo více direktivy. Když transformujete šablonu, musí se nainstaloval direktivy procesor, které lze řešit direktivy v šabloně.

 Direktivy fungovat tak, že přidáte kód ve třídě generovaného transformace. Direktivy lze volat z textové šablony a procesy modul direktivy volání při vytváření třídy generované transformace. Po zavolání metody direktivu úspěšně, můžete zbytek kód, který zapisuje v textové šablony spoléhají na funkce, která poskytuje direktivu. Například můžete provádět následující volání `import` direktivy v šabloně:

 `<#@ import namespace="System.Text" #>`

 Standardní procesoru direktiv převede na `using` příkaz ve třídě generovaného transformace. Pak můžete použít `StringBuilder` třídy ve zbývající části kódu šablony bez kvalifikace jej jako `System.Text.StringBuilder`.