---
title: Slovníček nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: f767d8e4-24d8-4803-80eb-e857202dbe2c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f074bf7b5c7077b1c4808d7d3035be0c6366d526
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842471"
---
# <a name="msbuild-glossary"></a>Slovníček nástroje MSBuild
Tyto podmínky se používají k popisu Microsoft Build Engine (MSBuild) a jeho součástí.

## <a name="glossary"></a>Slovníček
 Umístění registru AssemblyFoldersEx A kde externích dodavatelů ukládat cesty pro každou verzi rozhraní framework, které podporují, kde můžete zobrazit návrh čas rozlišení lze nalézt odkaz na sestavení.

 dávkování dávkování znamená, že dělení položek do různých kategorií známo jako *dávky*založená na metadata položky a pak spusťte cíl nebo úloha jeden čas pomocí jednotlivých dávek. Dávkování je ekvivalentem MSBuild pro--smyčky konstrukce. Další informace najdete v tématu [dávkování](../msbuild/msbuild-batching.md).

 sestavení sestavení scope oboru popisuje objekt MSBuild, třeba globální vlastností, která je potenciálně viditelný na projekt a všechny podřízené projekty, které jsou vytvořené v sestaveních s více projekty.

 podřízený projekt viz *projektu, podřízené*.

 Podmínka MSBuild mnoho prvků lze definovat podmíněně; To znamená `Condition` atributu se zobrazí v elementu. Obsah podmíněných prvků se ignoruje, pokud je podmínka vyhodnocena jako `true`. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).

 definice položky viz *položky definice*.

 Generování položky ve fázi spuštění sestavení, můžou vytvořit nebo upravit podle úloh, které mají podřízené položky `Output` prvky, které mají `ItemName` atribut. Úloha se říká, že "generování" nové položky.

 Generovat vlastnost během fáze spuštění sestavení, můžou vytvořit nebo upravit podle úloh, které mají podřízené vlastnosti `Output` prvky, které mají `PropertyName` atribut. Úloha se říká, že "generování" novou vlastnost.

 fáze hodnocení, které se vyžaduje vyhodnocení za první fáze sestavení projektu. Všechny vlastnosti a položky se vyhodnocují v pořadí, v jakém jsou uvedeny v projektu. Importované projekty jsou vyhodnocovány, jak se vyskytují v projektu. Cíle a úlohy se nespustí, dokud fáze spuštění a žádné vlastnosti nebo položky by deklarovat nebo generování ignorují během vyhodnocení.

 fáze spuštění, provádění se druhá fáze sestavení projektu. Vybrané cíle jsou integrované a jsou spouštěny úkoly. Může být vytvoření nebo úpravě vlastností a položek ve srovnání s jejich hodnoty hodnocení.

 Funkce, vlastnost viz *vlastnost funkce*.

 Funkce, položky viz položku funkce.

 Položka položky jsou vstupy do systému sestavení a jsou seskupeny do typů položek podle jejich názvy elementů. Položky obvykle představují soubory. Protože položky jsou pojmenovány podle typu položky patří do podmínky *položky* a *hodnota položky* zaměnitelné. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).

 skupinách definic položek definice položky obsahovat definice položek, které aplikacím dodávají výchozí metadat na libovolný typ položky. Stejně jako známých metadat je přidružen k všechny položky daného typu určenou položku metadat výchozí. V definici položky lze explicitně přepsat výchozí metadat. Další informace najdete v tématu [definice položek](../msbuild/item-definitions.md).

 funkce položek funkce položky získat informace o položkách v projektu. Tyto funkce zjednodušují získávání Distinct() položek a jsou rychlejší než položky ve smyčce. Nejsou k dispozici funkce pro manipulaci s cesty položky a řetězce. Další informace najdete v tématu [položky funkce](../msbuild/item-functions.md)

 položka metadat viz *metadata položky*.

 Typ položky typů položek jsou pojmenovány seznamy položek, které lze použít jako parametry pro úkoly. Úkoly pomocí hodnoty položek k provedení kroků procesu sestavení. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).

 metadata, metadata položky položky je kolekce dvojic název hodnota, která je přidružena položce. Metadata poskytuje popisné informace pro položku a je volitelné, s výjimkou dobře známé metadat. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).

 metadata, dobře známé známá metadata jsou jen pro čtení položky metadat, který je inicializován pomocí předdefinované hodnoty. Metadata známé poskytuje popisné informace pro položku, která odkazuje na soubor. Například hodnota dobře známé metadat s názvem `FullPath` je úplná cesta odkazovaný soubor. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).

 cílení na více verzí možnost pro aplikace nebo sestavení projekt cílit na mnoha různých CLR a rozhraní MSBuild a ze sady Visual Studio.

 Profilovat podmnožinu úplné rozhraní framework. To umožňuje minimalizovat, kterou je potřeba stáhnout do počítače.

 soubor projektu soubor projektu obsahuje MSBuild skript, který určuje sestavení. Soubory projektu obvykle mají příponu souboru, který končí *proj*, jako například *.csproj* nebo *.vbproj*. Soubory projektu mohou importovat soubory vlastnost a cílové soubory.

 Vlastnost A je pár klíč hodnota, která slouží k řízení procesu sestavení. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).

 vlastnosti prostředí vlastnost prostředí je vlastnost, která je automaticky inicializován na hodnotu proměnné prostředí systému, který má stejný název. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).

 Vlastnosti souboru A vlastnost soubor je soubor projektu, který obsahuje většinou vlastnosti skupin a skupin položek, které provedou sestavení. Podle konvence má příponu souboru *.props*. Soubory vlastností se importují obvykle na začátku přidružené soubory projektu.

 vlastnost, vlastností A funkcí je systémová vlastnost nebo metoda, která slouží k vyhodnocení skriptů nástroje MSBuild. Metody vlastností je možné přečíst systémový čas, porovnat řetězce, porovnat regulární výrazy a provádět jiné akce. Další informace najdete v tématu [funkce vlastností](../msbuild/property-functions.md).

 Vlastnosti funkce, vnořené funkce vlastností mohou být kombinovány do formuláře složitější funkce. Například

 `$([MSBuild]::BitwiseAnd(32,   $([System.IO.File]::GetAttributes(tempFile))))`

 Další informace najdete v tématu [funkce vlastností](../msbuild/property-functions.md).

 Vlastnosti globální že globální vlastnost je pár klíč hodnota, která slouží k řízení procesu sestavení. Globální vlastnosti jsou nastaveny na příkazovém řádku nebo pomocí `Properties` atribut [úlohy nástroje MSBuild](../msbuild/msbuild-task.md)a nelze změnit během fáze vyhodnocení sestavení. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).

 vlastnost, místní místní vlastnost je pár klíč hodnota, která slouží k řízení procesu sestavení. Tento termín slouží pouze k odlišení vlastnost, která není globální vlastnost.

 vlastnost, registru A registru vlastnost má hodnotu, která byla nastavena pomocí speciální syntaxe, která načte hodnotu podklíče registru systému. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).

 Vlastnost vyhrazené že vyhrazené vlastnost je pár klíč hodnota, která slouží k řízení procesu sestavení. Rezervované vlastnosti jsou automaticky inicializovány na předem definovaných hodnot. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).

 rozsah projektu. projekt oboru popisuje objekt MSBuild, například místní vlastnost, která je viditelná pouze v obsahující soubor projektu a všechny projekty, které importuje.

 projekt, podřízené A podřízený projekt vytvoří úkolu MSBuild během sestavování projektu. Tímto novým projektem je podřízený projekt, který obsahuje nebo importuje cíl, který obsahuje úkol MSBuild. Podřízený projekt dědí zadaná globální vlastnosti nadřazený projekt, pokud se změnil `Properties` atribut.

 seznam REDIST, na automatické distribuce signatur seznamu: seznam sestavení, které odpovídají dané rozhraní.

 sestavení referenční sestavení, který slouží k vytvoření aplikace v době návrhu. Referenční sestavení může mít skutečný kód a privátním rozhraním odebrány, byste museli opustit pouze metadata a veřejných rozhraní.

 Vlastnosti registru najdete v tématu *vlastnost, registru*.

 cílil A seskupuje úlohy v určitém pořadí a zpřístupňuje části souboru projektu jako vstupní body do procesu sestavení. Další informace najdete v tématu [cíle](../msbuild/msbuild-targets.md).

 cíl sestavení naleznete v cíli, spuštění.

 cíl, vyhodnocování kvůli přírůstková kompilace, cíle musí být analyzován na potenciálních změn vlastností a položek. I v případě, že je cíl vynechán, tyto změny musí provést. Vyhodnocení cíl znamená, že provádí tuto analýzu a provedení těchto změn. Další informace najdete v tématu [přírůstková sestavení](../msbuild/incremental-builds.md).

 cíl, provádění cíl provádění znamená, že vyhodnocení a provádění všech úloh, které mají žádné podmínky nebo jejíž podmínky vyhodnocen na hodnotu true. Během přírůstkové kompilace cíle může přeskočená nebo spustit, ale jsou vždy vyhodnoceny. Další informace najdete v tématu cílit, vyhodnocování.

 cíl, cíl, který má podmínku, která se vyhodnotí na hodnotu false s nespustil, to znamená, nemá žádný vliv na sestavení. Cíle, na kterých běží jsou proveden nebo vynechán. V obou případech se vyhodnotí cíl. Další informace najdete v tématu cílit, vyhodnocování.

 cíl, přeskočí, pokud se přírůstková kompilace Určuje, že všechny výstupní soubory jsou aktuální, pak je cíl vynechán, to znamená, se vyhodnotí cíl, ale nejsou provedeny úlohy v rámci cíle. Další informace najdete v tématu cílit, vyhodnocování.

 cílové rozhraní framework zástupný název, který popisuje rozhraní framework (například. NETFramework, Silverlight, atd.), verze a profilu (například klienta, Server atd.), který chcete cílit.

 Targeting pack v seznamu sestavení, které jsou distribuovány s danou architekturu a sadu referenčních sestavení pro dané rozhraní.

 cíle A cíle soubor je soubor projektu, který obsahuje většinou cíle a úlohy, které provede sestavení. Podle konvence má příponu souboru *.targets*. Cílové soubory obvykle importují na konci přidružené soubory projektu.

 Úloha úkoly jsou jednotky spustitelného kódu, který [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty používají k provádění operací sestavení. Úkol může například kompilovat vstupní soubory nebo spustit externí nástroj. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).

 Transformace A transformace je 1: 1 převod jednu položku kolekce do druhé. Kromě povolení projekt převést položky kolekce, umožňuje transformace cíl k identifikaci přímé mapování mezi její vstupy a výstupy. Další informace najdete v tématu [transformuje](../msbuild/msbuild-transforms.md).

 známá metadata viz *metadat, dobře známé*.

## <a name="see-also"></a>Viz také:
- [MSBuild](../msbuild/msbuild.md)