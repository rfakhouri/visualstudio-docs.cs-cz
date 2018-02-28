---
title: "Math – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Math object
ms.assetid: 607b94cb-921c-43cd-b514-fdbc13aeced6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f16fe4edf6a2a49db15d74abc8ebe6e53f955710
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="math-object-javascript"></a>Math – objekt (JavaScript)
Vnitřní objekt, který poskytuje funkce Základní matematika a konstanty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Math.[{property | method}]  
```  
  
## <a name="parameters"></a>Parametry  
 *Vlastnost*  
 Požadováno. Název vlastnosti **matematické**. objekt.  
  
 *– Metoda*  
 Požadováno. Název jedné z metod **matematické**. objekt.  
  
## <a name="remarks"></a>Poznámky  
 **Matematické** nelze vytvořit objekt pomocí **nové** operátor a vrátí chybu, pokud se pokusíte Uděláte to tak. Skriptovací stroj ji vytvoří, když je načten modulem. Všechny metody a vlastnosti jsou k dispozici pro váš skript za všech okolností.  
  
## <a name="requirements"></a>Požadavky  
 `Math` Objektu byla zavedena v [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)].  
  
<a name="js56jsobjmathprop"></a>   
## <a name="constants"></a>Konstanty  
 Následující tabulka uvádí konstanty `Math` objektu.  
  
|Konstanta|Popis|  
|--------------|-----------------|  
|[Math.e – konstanta](../../javascript/reference/math-constants-javascript.md)|Matematické konstanty e. Toto je Eulerova na číslo, je základ přirozeného logaritmu.|  
|[Math.ln2 – konstanta](../../javascript/reference/math-constants-javascript.md)|Přirozený logaritmus 2.|  
|[Math.ln10 – konstanta](../../javascript/reference/math-constants-javascript.md)|Přirozený logaritmus 10.|  
|[Math.log2e – konstanta](../../javascript/reference/math-constants-javascript.md)|Základní 2 logaritmu e.|  
|[Math.log10e – konstanta](../../javascript/reference/math-constants-javascript.md)|Základu 10 logaritmu e.|  
|[Math.PI – konstanta](../../javascript/reference/math-constants-javascript.md)|Pí. Toto je poměr obvodu kruh k jeho průměru.|  
|[Math.sqrt1_2 – konstanta](../../javascript/reference/math-constants-javascript.md)|Druhou odmocninu čísla 0,5 nebo, ekvivalentně, jeden dělený druhou odmocninu čísla 2.|  
|[Math.sqrt2 – konstanta](../../javascript/reference/math-constants-javascript.md)|Druhou odmocninu čísla 2.|  
  
<a name="js56jsobjmathmeth"></a>   
## <a name="functions"></a>Funkce  
 Následující tabulka uvádí funkce `Math` objektu.  
  
|Funkce|Popis|  
|--------------|-----------------|  
|[Math.Abs – funkce](../../javascript/reference/math-abs-function-javascript.md)|Vrátí absolutní hodnotu čísla.|  
|[Math.ACOS – funkce](../../javascript/reference/math-acos-function-javascript.md)|Vrátí Arkus kosinus čísla.|  
|[Math.acosh – funkce](../../javascript/reference/math-acosh-function-javascript.md)|Vrací hyperbolický Arkus kosinus (inverzní hyperbolický kosinus) čísla.|  
|[Math.ASIN – funkce](../../javascript/reference/math-asin-function-javascript.md)|Vrátí Arkus sinus čísla.|  
|[Math.asinh – funkce](../../javascript/reference/math-asinh-function-javascript.md)|Vrátí inverzní hyperbolický sinus čísla.|  
|[Math.Atan – funkce](../../javascript/reference/math-atan-function-javascript.md)|Vrátí Arkus tangens čísla.|  
|[Math.ATAN2 – funkce](../../javascript/reference/math-atan2-function-javascript.md)|Vrací úhel (v radiánech) z osy X do bodu reprezentována zadaný souřadnice y a x.|  
|[Math.atanh – funkce](../../javascript/reference/math-atanh-function-javascript.md)|Vrátí inverzní hyperbolický tangens čísla.|  
|[Math.ceil – funkce](../../javascript/reference/math-ceil-function-javascript.md)|Vrátí nejmenší celé číslo, které je větší než nebo rovna hodnotě zadané číselný výraz.|  
|[Math.cos – funkce](../../javascript/reference/math-cos-function-javascript.md)|Vrátí kosinus čísla.|  
|[Math.COSH – funkce](../../javascript/reference/math-cosh-function-javascript.md)|Vrátí hyperbolický kosinus čísla.|  
|[Math.exp – funkce](../../javascript/reference/math-exp-function-javascript.md)|Vrátí *e* (základ přirozeného logaritmu) umocněné na zadanou mocninu.|  
|[Math.expm1 – funkce](../../javascript/reference/math-expm1-function-javascript.md)|Vrátí výsledek odečtením 1 z e (základ přirozeného logaritmu) na zadanou mocninu).|  
|[Math.Floor – funkce](../../javascript/reference/math-floor-function-javascript.md)|Vrátí největší celé číslo, které je menší než nebo rovna zadané číselný výraz.|  
|[Math.hypot – funkce](../../javascript/reference/math-hypot-function-javascript.md)|Vrátí druhou odmocninu čísla součet kvadratických argumenty.|  
|[Math.imul – funkce](../../javascript/reference/math-imul-function-javascript.md)|Vrátí součin dvou čísel, které jsou považovány za 32bitová podepsaná celá čísla.|  
|[Math.log – funkce](../../javascript/reference/math-log-function-javascript.md)|Vrátí přirozený logaritmus čísla.|  
|[Math.log1p – funkce](../../javascript/reference/math-log1p-function-javascript.md)|Vrátí přirozený logaritmus 1 + číslo.|  
|[Math.LOG10 – funkce](../../javascript/reference/math-log10-function-javascript.md)|Vrátí logaritmus o základu 10 čísla.|  
|[Math.log2 – funkce](../../javascript/reference/math-log2-function-javascript.md)|Vrátí základní 2 logaritmus čísla.|  
|[Math.Max – funkce](../../javascript/reference/math-max-function-javascript.md)|Vrátí delší než zadaná dvou numerických výrazů.|  
|[Math.min – funkce](../../javascript/reference/math-min-function-javascript.md)|Vrátí menší dvou zadaných čísel.|  
|[Math.pow – funkce](../../javascript/reference/math-pow-function-javascript.md)|Vrací hodnotu výrazu základní na zadanou mocninu.|  
|[Math.Random – funkce](../../javascript/reference/math-random-function-javascript.md)|Vrátí pseudonáhodných číslo mezi 0 a 1.|  
|[Math.Round – funkce](../../javascript/reference/math-round-function-javascript.md)|Vrátí zadaný číselného výrazu zaokrouhlí na nejbližší celé číslo.|  
|[Math.Sign – funkce](../../javascript/reference/math-sign-function-javascript.md)|Vrátí znaménko čísla určující, zda je číslo kladné, záporné nebo 0.|  
|[Math.sin – funkce](../../javascript/reference/math-sin-function-javascript.md)|Vrátí sinus čísla.|  
|[Math.SINH – funkce](../../javascript/reference/math-sinh-function-javascript.md)|Vrátí inverzní hyperbolický sinus čísla.|  
|[Math.Sqrt – funkce](../../javascript/reference/math-sqrt-function-javascript.md)|Vrátí druhou odmocninu čísla.|  
|[Math.tan – funkce](../../javascript/reference/math-tan-function-javascript.md)|Vrátí tangens čísla.|  
|[Math.TANH – funkce](../../javascript/reference/math-tanh-function-javascript.md)|Vrátí hyperbolický tangens čísla.|  
|[Math.TRUNC – funkce](../../javascript/reference/math-trunc-function-javascript.md)|Vrátí celočíselnou část čísla odebrání všech míst za desetinnou čárkou.|  
  
## <a name="see-also"></a>Viz také  
 [JavaScript – objekty](../../javascript/reference/javascript-objects.md)   
 [Number – objekt](../../javascript/reference/number-object-javascript.md)