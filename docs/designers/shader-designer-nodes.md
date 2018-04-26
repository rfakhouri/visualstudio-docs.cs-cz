---
title: Uzly návrháře shaderů
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: f5192fbd-c78f-40a8-a4d4-443209610268
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fe4d73404f8794c2a5e4e64aef36198d78a0878
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="shader-designer-nodes"></a>Uzly návrháře shaderů
Články v této části dokumentace obsahují informace o různých shaderu Návrhář uzly, které můžete použít k vytvoření grafiky účinky.

## <a name="nodes-and-node-types"></a>Uzly a typy uzlů
 Návrhář shaderu představuje vizuálních efektů jako graf. Tyto grafy jsou vytvořeny z uzlů, které jsou speciálně vybrali a připojené přesné způsoby k dosažení určený vliv. Každý uzel reprezentuje část informace nebo matematické funkce a připojení mezi nimi představují tok informací prostřednictvím grafu k vytvoření výsledku. Návrhář shaderu obsahuje šest typy jiný uzel – filtry, texture uzly, parametry, konstanty, nástroj uzlů a uzly matematické – a několik jednotlivé uzly patří do každého typu. Tyto uzly a typy uzlů, které jsou popsané v další články v této části – najdete v odkazech na konci tohoto dokumentu.

## <a name="node-structure"></a>Struktura uzlu
 Všechny uzly se skládají z kombinace společné prvky. Každý uzel má aspoň jeden výstup terminálu na jeho pravé straně (s výjimkou uzlu konečnou barvu, který reprezentuje výstup shaderu). Uzly, které představují výpočty nebo vzorkovací texture body mají vstupní terminály na jejich levé strany, ale uzly, které představují informace mít žádné vstupní terminály. Výstup terminály jsou připojené k vstupní terminály přesunout informace z jednoho uzlu.

### <a name="promotion-of-inputs"></a>Povýšení vstupy
 Protože návrháře shaderu nakonec vygenerovat HLSL zdrojový kód tak, aby účinek mohou být používány hry nebo aplikace, Návrhář shaderu uzly se vztahují propagace typu pravidla, která používá HLSL. Vzhledem k tomu, že hardware grafiky funguje hlavně na hodnoty s plovoucí desetinnou čárkou, zadejte povýšení mezi různými typy – například od `int` k `float`, nebo z `float` k `double`– neobvyklé. Místo toho protože grafiky hardwaru používá stejnou operaci pro více položek najednou informací, jiný druh povýšení může dojít, ve kterém je velikost nejdéle vstupní posunut kratší počtu vstupy. Jak je posunut závisí na typ vstupu a také na operaci sám sebe:

-   **Je-li menší typ skalární hodnotu, pak:**

     Hodnota skalárních se replikují do vektor, který se rovná velikosti větší vstupu. Skalární vstup 5.0, například bude vektoru (5.0, 5.0, 5.0) po největší vstup operace tři element vektoru, bez ohledu na to, co je operaci.

-   **Pokud je typ menší vektor a operace se multiplikativní (\*, /, % a tak dále), pak:**

     Hodnota vektoru se zkopíruje do úvodní elementy vektor, který se rovná velikosti větší vstupu a koncové prvky jsou nastaveny na 1.0. Vstup vektoru (5.0, 5.0), například bude vektoru (5.0, 5.0, 1.0, 1.0) Pokud se násobí hodnotou vektoru čtyři element. Elementy třetí a čtvrtý výstupu se zachovají pomocí multiplikativní identity 1.0.

-   **Pokud je menší typ vektor a tuto operaci je sčítání (+,-, a tak dále), pak:**

     Hodnota vektoru se zkopíruje do úvodní elementy vektor, který se rovná velikosti větší vstupu a koncové prvky jsou nastaveny na 0,0. Vstup vektoru (5.0, 5.0), například bude vektoru (5.0, 5.0, 0,0, 0,0) při jejím přidání do vektoru čtyři elementu. Elementy třetí a čtvrtý výstupu se zachovají pomocí identitě doplňkové 0,0.

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Uzly konstanty](../designers/constant-nodes.md)|Popisuje uzlů, které můžete použít k reprezentaci literálových hodnot a interpolované vrchol stavu informace ve výpočtech shaderu. Protože vrchol stavu je interpolované – a proto se liší pro každý pixelů – každá instance pixelů shaderu obdrží jinou verzi konstanta.|
|[Uzly parametru](../designers/parameter-nodes.md)|Popisuje uzlů, které můžete použít k vyjádření polohy kamery, vlastnosti materiálu, osvětlení parametry, čas a další informace o aplikaci stavu ve výpočtech shaderu.|
|[Uzly textury](../designers/texture-nodes.md)|Popisuje uzly, které můžete použít k ukázkové různé typy texture a geometrie a k vytvoření nebo transformace texture souřadnice běžné způsoby.|
|[Matematické uzly](../designers/math-nodes.md)|Popisuje uzly, které můžete použít k provedení algebraických, logiku, trigonometrické a další matematické operace, které mapují přímo na HLSL pokyny.|
|[Uzly nástroje](../designers/utility-nodes.md)|Popisuje uzly, které můžete použít k provádění běžných osvětlení výpočty a dalších běžných operací, které se nemapují přímo na HLSL pokyny.|
|[Uzly filtru](../designers/filter-nodes.md)|Popisuje uzly, které můžete použít pro filtrování texture a filtrování barev.|