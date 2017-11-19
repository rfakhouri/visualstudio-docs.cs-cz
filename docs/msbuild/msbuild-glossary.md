---
title: "Slovníček nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f767d8e4-24d8-4803-80eb-e857202dbe2c
caps.latest.revision: "23"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: dccc0592d050a07f3682834b6f2a66e2f8c6eb7b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-glossary"></a>Slovníček nástroje MSBuild
Tyto podmínky se používají k popisu Microsoft Build Engine (MSBuild) a jeho komponenty.  
  
## <a name="glossary"></a>Slovníček  
 AssemblyFoldersEx  
 Umístění registru, kam dodavateli třetích stran ukládat cesty pro každou verzi rozhraní, které budou podporovat, kde můžete najít referenční sestavení zobrazit návrh doba řešení.  
  
 dávkování  
 Dávkování znamená dělení položek do různých kategorií, které jsou známé jako *dávek*, na základě metadata položky a poté spuštění cíl nebo úkolu jednou pomocí jednotlivých dávek. Dávkování je ekvivalentem MSBuild pro – cykly konstrukce. Další informace najdete v tématu [Batching](../msbuild/msbuild-batching.md).  
  
 sestavení oboru  
 Sestavení oboru popisuje nástroje MSBuild objektu, například globální vlastnost, která je potenciálně viditelné na projekt a všechny podřízené projekty, které jsou vytvořené v sestavení vícenásobného projektu.  
  
 podřízené projektu  
 V tématu *projektu, podřízené*.  
  
 Podmínka  
 Mnoho MSBuild prvků může být definováno podmíněně; To znamená `Condition` atributu se zobrazí v elementu. Obsah podmíněného elementů se ignoruje, pokud je podmínka vyhodnocena jako `true`. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).  
  
 definice, položky  
 V tématu *položky definice*.  
  
 Emitování položky  
 Během provádění fáze sestavení, může být položky vytvoření nebo úpravě úlohy, které mají podřízené `Output` prvky, které mají `ItemName` atribut. Úloha se říká "emitování" nové položky.  
  
 Emitování vlastnost  
 Během provádění fáze sestavení, může být vlastnosti vytvoření nebo úpravě úlohy, které mají podřízené `Output` prvky, které mají `PropertyName` atribut. Úloha se říká "emitování" novou vlastnost.  
  
 fáze hodnocení  
 Vyhodnocení je první fáze sestavení projektu. Všechny vlastnosti a položky jsou vyhodnocovány v pořadí, ve kterém se zobrazí v projektu. Importované projekty jsou vyhodnotit, jak se vyskytují v projektu. Cílů a úloh se nespustí, dokud fázi provádění a všech vlastností či položky jejich by deklarovat nebo emitování ignorují během vyhodnocení.  
  
 provádění fáze  
 Zpracování se druhé fáze sestavení projektu. Vybrané cíle jsou vytvořeny a spouštějí úlohy. Vlastností a položek můžete vytvořit nebo změnit ve srovnání s jejich vyhodnocení hodnoty.  
  
 Funkce, vlastnost  
 V tématu *vlastnost funkce*.  
  
 funkce položek  
 Najdete v části funkce položky.  
  
 položka  
 Položky jsou vstupy do systému sestavení a jsou seskupené do typů položek, které jsou založené na jejich názvy elementů. Položky obvykle představují soubory. Protože položky jsou pojmenované podle typu položky patří do podmínky *položky* a *hodnota položky* zaměnitelné. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).  
  
 definice položek  
 Položka definice skupiny obsahují definice položek, které přidat výchozí metadata do libovolného typu položky. Jako dobře známé metadata je spojeno s všechny položky daného typu určenou položku Výchozí metadata. V definici položky lze explicitně přepsat výchozí metadat. Další informace najdete v tématu [definice položek](../msbuild/item-definitions.md).  
  
 funkce položek  
 Funkce položek získat informace o položkách v projektu. Tyto funkce zjednodušit získávání Distinct() položky a je rychlejší než ve smyčce přes položky. Jsou funkce k manipulaci s položky cesty a řetězce. Další informace najdete v tématu [funkce položek](../msbuild/item-functions.md)  
  
 metadata položky  
 V tématu *metadata, položka*.  
  
 Typ položky  
 Typy položek jsou pojmenované seznam položek, které lze použít jako parametry pro úlohy. Úlohy pomocí hodnot položky podle kroků procesu sestavení. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).  
  
 metadata, položky  
 Metadata položek je kolekci dvojic název hodnota, která je přidružená položce. Metadata poskytuje popisné informace pro položku a je volitelné, s výjimkou dobře známé metadat. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).  
  
 metadata známé  
 Metadata známé se metadata položky jen pro čtení, který je inicializován s použitím předdefinované hodnoty. Metadata známé poskytuje popisné informace pro položku, která odkazuje na soubor. Například hodnota dobře známé metadat s názvem `FullPath` je úplná cesta k souboru odkazované. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).  
  
 cílení na více verzí  
 Možnost pro projekt aplikace nebo sestavení pro mnoho různých CLR a rozhraní z nástroje MSBuild a ze sady Visual Studio.  
  
 Profil  
 Podmnožinu rozhraní úplné. Používá se k minimalizaci množství, které musí být stažena do počítače.  
  
 soubor projektu  
 Obsahuje soubor projektu nástroje MSBuild skript, který řídí sestavení. Soubory projektu obvykle mají příponu souboru, který končí řetězcem "proj", jako je například .csproj nebo .vbproj. Soubory projektu může importovat vlastnost soubory a soubory cíl.  
  
 property  
 Vlastnost je pár klíč hodnota, která se používá k řízení procesu sestavení. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  
  
 vlastnost, prostředí  
 Ve vlastnosti prostředí je vlastnost, která je automaticky inicializován na hodnotu proměnné prostředí systému, která má stejný název. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  
  
 vlastnost souboru  
 Vlastnost soubor je soubor projektu, který obsahuje většinou vlastnost skupin a skupin položky, které průvodce sestavení. Podle konvence je props příponu souboru. Vlastnost soubory jsou obvykle importovat na začátku soubory přidružené projektu.  
  
 vlastnost, – funkce  
 Vlastnost funkce je systém vlastnosti nebo metody, který slouží k vyhodnocení nástroje MSBuild skripty. Vlastnost metody slouží ke čtení systémového času, porovnání řetězců, regulární výrazy shody a provádět další akce. Další informace najdete v tématu [funkce vlastností](../msbuild/property-functions.md).  
  
 Vlastnost funkce, vnořené  
 Funkce vlastností mohou být kombinovány do formuláře složitější funkce. Například  
  
 `$([MSBuild]::BitwiseAnd(32,   $([System.IO.File]::GetAttributes(tempFile))))`  
  
 Další informace najdete v tématu [funkce vlastností](../msbuild/property-functions.md).  
  
 vlastnost, globální  
 Globální vlastnost je pár klíč hodnota, která se používá k řízení procesu sestavení. Globální vlastnosti jsou nastaveny na příkazovém řádku nebo pomocí `Properties` atribut [úlohy nástroje MSBuild](../msbuild/msbuild-task.md)a nelze jej změnit během zkušební fáze sestavení. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  
  
 vlastnost, místní  
 Místní vlastnost je pár klíč hodnota, která se používá k řízení procesu sestavení. Tento termín se používá pouze pro rozlišení vlastnost, která není globální vlastnost.  
  
 vlastnost, registru  
 Vlastnost registru má hodnotu, která je nastavena pomocí speciální syntaxe, který čte hodnotu podklíče registru systému. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  
  
 vlastnost, vyhrazena  
 Vyhrazené vlastnost je pár klíč hodnota, která se používá k řízení procesu sestavení. Rezervované vlastnosti jsou automaticky inicializován s předdefinovanými hodnotami. Další informace najdete v tématu [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md).  
  
 rozsah projektu  
 Rozsah projektu popisuje nástroje MSBuild objektu, například místní vlastnosti, které se zobrazuje jenom v obsahující souboru projektu a na všechny projekty, které se importuje.  
  
 projekt, podřízené  
 Úlohy nástroje MSBuild podřízeného projektu vytvoří při sestavování projektu. Tento nový projekt je podřízená projekt, který obsahuje nebo importuje cíl, který obsahuje úlohu MSBuild. Projekt podřízené dědí vlastnosti globálních nadřazeného projektu, pokud jsou upraveném `Properties` atribut.  
  
 seznam Redistribuce  
 Seznam Redistribuce: seznam sestavení, které odpovídají dané rozhraní.  
  
 odkaz na sestavení  
 Sestavení, která se používá při návrhu k vytvoření aplikace. Referenční sestavení může mít kód a privátním rozhraním odebrat z něj ponechat pouze metadata a veřejné rozhraní.  
  
 Vlastnost registru  
 V tématu *vlastnost, registru*.  
  
 cíl  
 Cíl společně skupiny úloh v určitém pořadí a zpřístupňuje části souboru projektu jako vstupní body do procesu sestavení. Další informace najdete v tématu [cíle](../msbuild/msbuild-targets.md).  
  
 cíl, sestavení  
 Najdete v tématu cíle, spuštěná.  
  
 cíl, vyhodnocení  
 Z důvodu přírůstkové kompilace musí být analyzovány cíle pro potenciální změny vlastností a položek. I v případě, že cíl bylo přeskočeno, je nutné provést tyto změny. Vyhodnocení cíl znamená provádění této analýze a provedení těchto změn. Další informace najdete v tématu [přírůstková sestavení](../msbuild/incremental-builds.md).  
  
 cíl, provádění  
 Provádění cíl znamená vyhodnocení a provádění všech úloh, které mají žádné podmínky nebo jejichž podmínky vyhodnotit na hodnotu true. Během přírůstkové kompilace cíle může být přeskočeno nebo provést, ale jsou vždy vyhodnoceny. Další informace najdete v tématu cíle, vyhodnocení.  
  
 cíl, systémem  
 Cíl, který má podmínku, kterou vyhodnocena jako false není spuštěna, to znamená, nemá žádný vliv na sestavení. Cíle, které spustit jsou provést nebo přeskočena. V obou případech je vyhodnocován cíl. Další informace najdete v tématu cíle, vyhodnocení.  
  
 cíl, přeskočení  
 Když přírůstkové kompilace zjistí, všechny výstupní soubory jsou aktuální, pak cíle bylo přeskočeno, to znamená, vyhodnotí cíl, ale nejsou provést úkoly v rámci cíle. Další informace najdete v tématu cíle, vyhodnocení.  
  
 Cílový framework Přezdívka  
 Název, který popisuje rozhraní (například. NETFramwork, Silverlight, atd.), verze a profilu (například klienta, serveru atd.), který chcete cílit.  
  
 cílení na pack  
 Seznam sestavení, které jsou distribuované s danou rozhraní a sada referenční sestavení dané platformy.  
  
 soubor cíle  
 Cíle soubor je soubor projektu, který obsahuje většinou cílů a úloh, které průvodce sestavení. Podle konvence je .targets příponu souboru. Cílové soubory jsou obvykle importovat na konci soubory přidružené projektu.  
  
 – úloha  
 Úlohy jsou jednotky spustitelného kódu, který [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty používají k provádění operací sestavení. Úloha může být například kompilaci vstupní soubory nebo spuštění externího nástroje. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  
  
 transform  
 Transformace je 1: 1 převod jednu položku kolekce do druhé. Kromě povolení projekt k převodu kolekce položek, umožňuje transformace cíl k identifikaci přímého mapování mezi jeho vstupů a výstupů. Další informace najdete v tématu [transformuje](../msbuild/msbuild-transforms.md).  
  
 dobře známé metadat  
 V tématu *metadata, dobře známé*.  
  
## <a name="see-also"></a>Viz také  
 [Nástroje MSBuild](../msbuild/msbuild.md)