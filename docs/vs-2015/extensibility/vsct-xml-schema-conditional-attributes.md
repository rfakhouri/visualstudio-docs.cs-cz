---
title: Podmíněné atributy schématu VSCT XML | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, conditional attributes
- conditional attributes (VSCT XML schema)
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6294ee8027b61840149096561efc91b8a4a3c3ec
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54774750"
---
# <a name="vsct-xml-schema-conditional-attributes"></a>Podmíněné atributy XML schématu VSCT
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Podmíněné atributy se můžou vztahovat na všechny seznamy a položky. Logické operátory a výrazy rozšíření symbol vyhodnocen na hodnotu true nebo false. Pokud je hodnota true, jsou přidružený seznam nebo položka je součástí výsledný výstup.  
  
 Rozšíření token lze testovat pro jiné token rozšíření nebo konstanty. Funkce Defined() slouží k otestování, jestli se definovala konkrétní název, i když nemá žádnou hodnotu.  
  
 Při použití atributu podmínky do seznamu podmínka platí pro každý podřízený prvek v seznamu. Obsahuje-li podřízeného elementu samotného atributu podmínky, potom stavu je v kombinaci se nadřazený výraz a operací.  
  
 Hodnoty 1, '1' a 'true' jsou vyhodnoceny jako PRAVDA a 0, "0" a "false" se vyhodnotí jako false.  
  
## <a name="operators"></a>Operátory  
 Následující operátory může použít k vyhodnocení podmíněné výrazy.  
  
|Operátor|Definice|  
|--------------|----------------|  
|(,)|Seskupování|  
|!|Logický operátor not|  
|\<, >, \<=, >=, ==, !=|Relační a rovnost|  
|and|Boolean|  
|or|Boolean|  
  
## <a name="examples"></a>Příklady  
  
```  
<Menu Condition="Defined(DEBUG)" …  
</Menu>  
  
<Menu Condition="%(SKU_MODE) = 'Demo'" …  
</Menu>  
  
<Menus Condition="Defined(DEBUG)">  
    <Menu …  
    </Menu>  
</Menus>  
  
<Menus Condition="Defined(DEMO_SKU)">  
    <Menus Condition="!Defined(DEBUG)">  
        <Menu …  
        </Menu>  
    </Menus>  
  
    <Menu …  
    </Menu>  
</Menus>  
  
<Menus Condition="(Defined(DEMO_SKU) or Defined(SAMPLE_SKU))   
and !Defined(DEBUG)">  
    <Menu …  
    </Menu>  
</Menus>  
```  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
