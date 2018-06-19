---
title: Object.is – funkce (JavaScript) | Microsoft Docs
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
ms.assetid: 6e2f6c6d-7cd2-47c4-a513-3ba53988d27d
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 36d4c281fdafbfacb0b1f6061ef4a90bfac99234
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791118"
---
# <a name="objectis-function-javascript"></a>Object.is – funkce (JavaScript)
Vrátí hodnotu, která určuje, zda jsou dvě hodnoty stejnou hodnotu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.is(value1, value2)  
```  
  
#### <a name="parameters"></a>Parametry  
 `value1`  
 Požadováno. První hodnota k testování.  
  
 `value2`  
 Požadováno. Druhá hodnota k testování.  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud je hodnota stejnou hodnotu; v opačném `false`.  
  
## <a name="remarks"></a>Poznámky  
 Na rozdíl od == – operátor, `Object.is` není coerce všechny typy – při testování hodnoty.  
  
 Porovnání používaný službou `Object.is` je podobná porovnání používaný službou === operátor, vyjma toho, že `Object.is` zpracovává `Number.isNaN` jako stejnou hodnotu jako `NaN`. Je také vyhodnotí + 0 a - 0 jako různé hodnoty.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]