---
title: "Číslo konstanty (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- POSITIVE_INFINITY constant [JavaScript]
- MAX_VALUE constant [JavaScript]
- MIN_VALUE constant [JavaScript]
- number constants [JavaScript]
- Number.NEGATIVE_INFINITY constant [JavaScript]
- Number.POSITIVE_INFINITY constant [JavaScript]
- NEGATIVE_INFINITY constant [JavaScript]
- NaN constant [JavaScript]
- Number.MIN_VALUE constant [JavaScript]
- constants [JavaScript], number
- Number.NaN constant [JavaScript]
- Number.MAX_VALUE constant [JavaScript]
ms.assetid: e0701b41-99ae-4916-9ec0-f79bb15386fb
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f846ef7cbd9609f7913d6305e48cb4942476ca21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="number-constants-javascript"></a>Číselné konstanty (JavaScript)
Následující číselné konstanty jsou vlastnosti `Number` objektu.  
  
## <a name="number-object-constants"></a>Číselné konstanty objektu  
 Nemáte k vytvoření `Number` objekt, který má přístup k tyto konstanty.  
  
|Konstanta|Hodnota vrácená|  
|--------------|--------------------|  
|`Number.EPSILON`|Nejmenší číslo, které může být reprezentován v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Rovná přibližně 2.2204460492503130808472633361816E-16.|  
|`Number.MAX_SAFE_INTEGER`|Největší číslo, které může být reprezentován bezpečně v jazyce JavaScript. Rovno 9007199254740991.|  
|`Number.MAX_VALUE`|Největší číslo, které může být reprezentován v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Rovno přibližně 1, 79E + 308.|  
|`Number.MIN_SAFE_INTEGER`|Nejmenší číslo, které může být reprezentován bezpečně v jazyce JavaScript. Rovno-9007199254740991.|  
|`Number.MIN_VALUE`|Nejbližší číslo nule, který může být reprezentován v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Rovná přibližně 5.00E-324.|  
|`Number.NaN`|Hodnota, která není číslo.<br /><br /> V porovnání rovnosti `NaN` se nerovná jakákoli hodnota, včetně sám sebe. K ověření, zda je hodnota ekvivalentní `NaN`, použijte [funkce isNaN](../../javascript/reference/isnan-function-javascript.md).|  
|`Number.NEGATIVE_INFINITY`|Hodnotu, která je menší než největší záporné číslo, které může být reprezentován v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].<br /><br /> [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]Zobrazí `NEGATIVE_INFINITY` hodnoty jako `-infinity`.|  
|`Number.POSITIVE_INFINITY`|Hodnota větší než největší číslo, které může být reprezentován v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].<br /><br /> [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]Zobrazí `POSITIVE_INFINITY` hodnoty jako `infinity`.|  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 Pro `Number.EPSILON`, `Number.MAX_SAFE_INTEGER`, a `Number.MIN_SAFE_INTEGER`:  
  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **Platí pro**: [číslo objektu](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Matematické konstanty](../../javascript/reference/math-constants-javascript.md)   
 [Konstanty jazyka JavaScript](../../javascript/reference/javascript-constants.md)   
 [Infinity – konstanta](../../javascript/reference/infinity-constant-javascript.md)   
 [NaN – konstanta](../../javascript/reference/nan-constant-javascript.md)   
 [isNaN – funkce](../../javascript/reference/isnan-function-javascript.md)