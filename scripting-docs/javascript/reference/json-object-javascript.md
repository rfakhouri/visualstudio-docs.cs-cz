---
title: Objekt JSON (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: JSON
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: JSON object
ms.assetid: 0279a0e0-70bf-451a-a78e-0da4e2fdeb9a
caps.latest.revision: "43"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5310132368f665c6734c469a67636d33a08858d4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="json-object-javascript"></a>JSON – objekt (JavaScript)
Vnitřní objekt, který poskytuje funkce pro převod [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hodnoty do a z formátu JavaScript Object Notation (JSON). `JSON.stringify` Funkce serializuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hodnotu na JSON text. `JSON.parse` Funkce deserializuje text JSON k vytvoření [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hodnotu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
JSON.[method]  
  
```  
  
## <a name="parameters"></a>Parametry  
 `Method`  
 Požadováno. Název jedné z metod `JSON` objektu.  
  
## <a name="remarks"></a>Poznámky  
 Nelze vytvořit `JSON` objekt pomocí `new` operátor. Jestliže se to pokusíte provést, dojde k chybě. Však můžete přepsat nebo upravit `JSON` objektu.  
  
 Vytvoří skriptovacího stroje `JSON` objektu při načtení modulu. Jeho metody jsou k dispozici pro váš skript po celou dobu.  
  
 Použít vnitřní `JSON` objektu, ujistěte se, že není tyto prvky přepsat s jinou `JSON` objekt, který je definován ve vašem skriptu. Budete muset upravit existující příkazy skriptu, které zjistit přítomnost `JSON` objekt, protože tyto příkazy vyhodnotí jinak. To je patrné z následujícího příkladu.  
  
```JavaScript  
if (!this.JSON) {  
    // JSON object does not exist.  
    }  
```  
  
 V předchozím příkladu `!this.JSON` vyhodnocena jako false v [!INCLUDE[jsv58text](../../javascript/reference/includes/jsv58text-md.md)]. Proto kód uvnitř `if` příkaz nepracuje.  
  
## <a name="functions"></a>Funkce  
 [JSON.Parse – funkce](../../javascript/reference/json-parse-function-javascript.md)  
  
 [JSON.stringify – funkce](../../javascript/reference/json-stringify-function-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv58](../../javascript/reference/includes/jsv58-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [tojson – metoda (Date)](../../javascript/reference/tojson-method-date-javascript.md)   
 [JavaScript – objekty](../../javascript/reference/javascript-objects.md)   
 [Centrum šablony ukázkovou aplikaci (pro Windows Store)](http://code.msdn.microsoft.com/Hub-template-sample-with-4b70002d)