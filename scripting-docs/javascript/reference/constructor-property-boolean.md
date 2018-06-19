---
title: constructor – vlastnost (logická hodnota) | Microsoft Docs
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
ms.assetid: b67ca875-23c6-4687-a5ce-1cdd25d1c923
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 091da5342c4713c8eba646a8bd78c315a6a0fa48
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790311"
---
# <a name="constructor-property-boolean"></a>constructor – vlastnost (logická hodnota)
Určuje funkce, která vytvoří logickou hodnotu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
boolean.constructor([[value])  
```  
  
#### <a name="parameters"></a>Parametry  
 `boolean`  
 Název logická hodnota.  
  
 `value`  
 Volitelné. Určuje hodnotu logickou hodnotu. To může být čísla 1 nebo 0, nebo řetězce "true", nebo "Nepravda".  
  
## <a name="remarks"></a>Poznámky  
 `constructor` Vlastnost obsahuje odkaz na funkci, která vytvoří instanci objektu Boolean.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití vlastnosti konstruktor.  
  
```JavaScript  
var x = new Boolean("true");  
  
if (x.constructor == Boolean)  
    document.write("Object is a Boolelan.");  
  
// Output:  
// Object is a Boolean.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]