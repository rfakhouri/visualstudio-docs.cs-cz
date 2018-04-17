---
title: Podmíněné atributy schématu VSCT XML | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, conditional attributes
- conditional attributes (VSCT XML schema)
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 975ca2f5fa6f070baf07b26cbfa0d8c3aa3b67d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vsct-xml-schema-conditional-attributes"></a>Podmíněné atributy schématu VSCT XML
Podmíněné atributy může být použity na všechny seznamy a položky. Logické operátory a výrazy rozšíření symbol vyhodnotí jako true nebo false. V případě hodnoty true, jsou přidružený seznam nebo položka je součástí výsledný výstup.  
  
 Token rozšíření může být porovnávaný další token rozšiřuje nebo konstanty. Funkce Defined() se používá k ověření, zda byla definována konkrétní název, i když nemá žádnou hodnotu.  
  
 Stav atributu se použije k seznamu, podmínky platí pro každý podřízený element v seznamu. Pokud podřízený element samotné obsahuje atribut podmínku, pak jeho podmínky spolu s výraz nadřazené a operace.  
  
 Hodnoty 1, '1' a 'true', jsou vyhodnoceny jako true, a 0, "0", "Nepravda", jsou vyhodnoceny jako false.  
  
## <a name="operators"></a>Operátory  
 Následující operátory slouží k vyhodnocení podmíněné výrazy.  
  
|Operátor|Definice|  
|--------------|----------------|  
|(,)|Seskupování|  
|!|Logický operátor not|  
|\<, >, \<=, >=, ==, !=|Relační a rovnosti|  
|and|Boolean|  
|or|Boolean|  
  
## <a name="examples"></a>Příklady  
  
```  
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
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)