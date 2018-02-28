---
title: "Boolean – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- boolean_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Boolean object
- Boolean data type, Boolean object
ms.assetid: d67748f2-7bf5-4889-8269-e777616cc5f0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20695376e4935cf6ddc34f30e373df19575ece3f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="boolean-object-javascript"></a>Boolean – objekt (JavaScript)
Vytvoří novou logickou hodnotu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
boolObj = new Boolean([boolValue])  
```  
  
## <a name="parameters"></a>Parametry  
 `boolObj`  
 Požadováno. Název proměnné, do kterého `Boolean` objekt je přiřazen.  
  
 `boolValue`  
 Volitelné. Počáteční logickou hodnotu pro nový objekt. Pokud `boolvalue` je vynechán nebo je `false`, 0, `null`, `NaN`, nebo je prázdný řetězec, počáteční hodnota logická hodnota objektu `false`. Jinak je počáteční hodnota `true`.  
  
## <a name="remarks"></a>Poznámky  
 `Boolean` Objekt je obálka pro datový typ Boolean. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]implicitně používá `Boolean` vždy, když Boolean – datový typ je převést na objekt `Boolean` objektu.  
  
 Zřídka doložit `Boolean` explicitně objektu.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `Boolean` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[constructor – vlastnost](../../javascript/reference/constructor-property-boolean.md)|Určuje funkce, která vytvoří logickou hodnotu.|  
|[prototype – vlastnost](../../javascript/reference/prototype-property-boolean.md)|Vrátí odkaz na prototypu pro logickou hodnotu.|  
  
<a name="js56jsobjarraymeth"></a>   
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Boolean` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[toString – metoda](../../javascript/reference/tostring-method-boolean-1.md)|Vrátí řetězcovou reprezentaci logickou hodnotu.|  
|[valueOf – metoda](../../javascript/reference/valueof-method-boolean.md)|Získá odkaz booleovskou hodnotu.|  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]