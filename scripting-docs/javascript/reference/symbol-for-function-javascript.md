---
title: Symbol.for – funkce (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 27db15f3-9108-4892-8f89-e84031729cb6
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b7e47c00fbaa321d71a3eeba79e523eee719fb2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791406"
---
# <a name="symbolfor-function-javascript"></a>Symbol.for – funkce (JavaScript)
Vrátí symbol pro zadaný klíč, nebo pokud klíč neexistuje, vytvoří nový objekt symbol pomocí nového klíče.  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
Symbol.for(key);  
```  
  
#### <a name="parameters"></a>Parametry  
 `key`  
 Požadováno. Klíč pro symbol, který se používá jako popis.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vyhledá symbol v registru globální symbol. Pokud jste serializovat symboly jako řetězce, ujistěte se, že konkrétní řetězec mapuje na správný symbol pro vyhledávání všech pomocí registru globální symbol.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
var sym = Symbol.for("desc");  
  
console.log(sym.toString());  
  
// Two different object references.  
console.log(Symbol("symbol") === Symbol.for("symbol");)  
// Single object reference.   
console.log(Symbol.for("symbol") === Symbol.for("symbol");)  
  
// Output:  
// Symbol(desc);  
// false  
// true  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]