---
title: Podmíněné atributy schématu VSCT XML | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, conditional attributes
- conditional attributes (VSCT XML schema)
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 11807129c34fa613ef06b3534adc7c7ebb9865e0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322942"
---
# <a name="vsct-xml-schema-conditional-attributes"></a>Podmíněné atributy VSCT XML schématu
Podmíněné atributy můžete použít pro všechny seznamy a položky. Logické operátory a výrazy rozšíření symbol vyhodnocen na hodnotu true nebo false. Pokud je hodnota true, jsou přidružený seznam nebo položka je součástí výsledný výstup.

 Můžete otestovat token rozšíření pro jiné token rozšíření nebo konstanty. Funkce `Defined()` testuje, jestli se definovala konkrétní název, i když nemá žádnou hodnotu.

 Při použití atributu podmínky do seznamu podmínka platí pro každý podřízený prvek v seznamu. Obsahuje-li podřízeného elementu samotného atributu podmínky, potom stavu je v kombinaci se nadřazený výraz a operací.

 Hodnoty 1, '1' a 'true' jsou vyhodnoceny jako PRAVDA a 0, "0" a "false" se vyhodnotí jako false.

## <a name="operators"></a>Operátory
 Použijte následující operátory k vyhodnocení podmíněné výrazy.

|Operátor|Definice|
|--------------|----------------|
|(,)|Seskupování|
|!|Logický operátor not|
|\<, >, \<=, >=, ==, !=|Relační a rovnost|
|and|Boolean|
|or|Boolean|

## <a name="examples"></a>Příklady

```xml
<Menu Condition="Defined(DEBUG)" ...
</Menu>

<Menu Condition="%(SKU_MODE) = 'Demo'" ...
</Menu>

<Menus Condition="Defined(DEBUG)">
    <Menu ...
    </Menu>
</Menus>

<Menus Condition="Defined(DEMO_SKU)">
    <Menus Condition="!Defined(DEBUG)">
        <Menu ...
        </Menu>
    </Menus>

    <Menu ...
    </Menu>
</Menus>

<Menus Condition="(Defined(DEMO_SKU) or Defined(SAMPLE_SKU))
and !Defined(DEBUG)">
    <Menu ...
    </Menu>
</Menus>
```

## <a name="see-also"></a>Viz také:
- [Visual Studio tabulky příkazů (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)