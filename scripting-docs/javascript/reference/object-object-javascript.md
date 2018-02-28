---
title: Objekt objekt (JavaScript) | Microsoft Docs
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
- object
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Object object
ms.assetid: d24ef8fc-217b-4828-94e1-19f72780bae0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17e82b9c66c286c7f847e7b67b1b5928aadd613e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="object-object-javascript"></a>Object – objekt (JavaScript)
Poskytuje funkce, které jsou společné pro všechny [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
obj  
 = new Object([value])   
```  
  
## <a name="parameters"></a>Parametry  
 `obj`  
 Požadováno. Název proměnné, do kterého `Object` objekt je přiřazen.  
  
 *Hodnota*  
 Volitelné. Kterákoli z [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] primitivní datové typy (číslo, logická hodnota nebo řetězec). Pokud hodnota objektu, se vrátí objekt beze změny. Pokud *hodnotu* je `null`, **nedefinované**, nebo není zadaná, je vytvořen objekt s žádný obsah.  
  
## <a name="remarks"></a>Poznámky  
 `Object` Objektu se nachází v jiných [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty; všechny její metody a vlastnosti, které jsou k dispozici v všechny ostatní objekty. Metody můžete jej předefinovat v uživatelem definované objekty a jsou volány [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] v příslušnou dobu. **ToString** metoda je příkladem často Předefinovaná `Object` metoda.  
  
 V této referenční příručka jazyka popis každého `Object` metoda obsahuje výchozí a specifický pro objekt implementace informace vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty.  
  
## <a name="requirements"></a>Požadavky  
 `Object Object` Byla zavedena v [!INCLUDE[jsv3text](../../javascript/reference/includes/jsv3text-md.md)]. Některé členy v následujících seznamech byly zavedeny v pozdějších verzích.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `Object Object`.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[__proto\_ \_ vlastnost](../../javascript/reference/proto-property-object-javascript.md)|Určuje prototyp objektu.|  
|[constructor – vlastnost](../../javascript/reference/constructor-property-object-javascript.md)|Určuje funkci, která vytvoří objekt.|  
|[prototype – vlastnost](../../javascript/reference/prototype-property-object-javascript.md)|Vrátí odkaz na prototyp třídy objektů.|  
  
## <a name="functions"></a>Funkce  
 Následující tabulka uvádí funkce `Object Object`.  
  
|Funkce|Popis|  
|--------------|-----------------|  
|[Object.Assign – funkce](../../javascript/reference/object-assign-function-object-javascript.md)|Zkopíruje hodnoty ze jeden nebo více objektů zdrojového na cílový objekt.|  
|[Object.Create – funkce](../../javascript/reference/object-create-function-javascript.md)|Vytvoří objekt, který má zadaný prototypu a volitelně obsahující zadané vlastnosti.|  
|[Object.defineproperties – funkce](../../javascript/reference/object-defineproperties-function-javascript.md)|Přidá jeden nebo více vlastností do objektu nebo upravuje atributy existující vlastnosti.|  
|[Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md)|Přidá vlastnost do objektu nebo upravuje atributy existující vlastnost.|  
|[Object.freeze – funkce](../../javascript/reference/object-freeze-function-javascript.md)|Zabrání se úpravě existující vlastnost atributy a hodnoty a zabrání přidání nových vlastností.|  
|[Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)|Vrátí definici vlastnosti dat nebo přistupujícího objektu vlastnosti.|  
|[Object.getownpropertynames – funkce](../../javascript/reference/object-getownpropertynames-function-javascript.md)|Vrátí názvy vlastnosti a metody objektu.|  
|[Object.getownpropertysymbols – funkce](../../javascript/reference/object-getownpropertysymbols-function-javascript.md)|Vrátí symbol vlastnosti objektu.|  
|[Object.getprototypeof – funkce](../../javascript/reference/object-getprototypeof-function-javascript.md)|Vrací prototyp objektu.|  
|[Object.is – funkce](../../javascript/reference/object-is-function-javascript.md)|Vrátí hodnotu, která určuje, zda jsou dvě hodnoty stejnou hodnotu.|  
|[Object.isextensible – funkce](../../javascript/reference/object-isextensible-function-javascript.md)|Vrátí hodnotu, která určuje, zda nové vlastnosti lze přidat do objektu.|  
|[Object.isfrozen – funkce](../../javascript/reference/object-isfrozen-function-javascript.md)|Vrátí `true` Pokud existující vlastnost atributy a hodnoty nemůže být upraven v objektu, a nové vlastnosti nelze přidat k objektu.|  
|[Object.issealed – funkce](../../javascript/reference/object-issealed-function-javascript.md)|Vrátí `true` Pokud existující atributy vlastnost nemůže být upravena v objektu, a nové vlastnosti nelze přidat k objektu.|  
|[Object.Keys – funkce](../../javascript/reference/object-keys-function-javascript.md)|Vrátí názvy výčtové vlastnosti a metody objektu.|  
|[Object.preventextensions – funkce](../../javascript/reference/object-preventextensions-function-javascript.md)|Zabraňuje přidání nových vlastností do objektu.|  
|[Object.Seal – funkce](../../javascript/reference/object-seal-function-javascript.md)|Zabrání se úpravě atributů existující vlastnosti a brání přidání nových vlastností.|  
|[Object.setprototypeof – funkce](../../javascript/reference/object-setprototypeof-function-javascript.md)|Nastaví prototyp objektu.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Object Object`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[hasOwnProperty – metoda](../../javascript/reference/hasownproperty-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda má objekt vlastnost se zadaným názvem.|  
|[isPrototypeOf – metoda](../../javascript/reference/isprototypeof-method-object-javascript.md)|Vrátí logickou hodnotu, která určuje, zda objekt existuje v hierarchii prototypu jiný objekt.|  
|[propertyIsEnumerable – metoda](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda zadaná vlastnost je součástí objektu a zda je vyčíslitelná.|  
|[toLocaleString – metoda](../../javascript/reference/tolocalestring-method-object-javascript.md)|Vrátí objekt převést na řetězec v závislosti na aktuální národní prostředí.|  
|[toString – metoda](../../javascript/reference/tostring-method-object-javascript.md)|Vrátí řetězcovou reprezentaci objektu.|  
|[valueOf – metoda](../../javascript/reference/valueof-method-object-javascript.md)|Vrátí primitivní hodnotu zadaného objektu.|  
  
## <a name="see-also"></a>Viz také  
 [JavaScript – objekty](../../javascript/reference/javascript-objects.md)