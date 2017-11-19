---
title: "String.RAW – funkce (JavaScript) | Microsoft Docs"
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
ms.assetid: b1038b73-3944-4645-b075-3a674b313762
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53df2bf0e455da8b1ccc6de3cbf3f4e3ebee4c09
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="stringraw-function-javascript"></a>String.raw – funkce (JavaScript)
Vrátí Nezpracovaný řetězec formátu řetězec šablony.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
String.raw`templateStr`;  
String.raw(obj, ...substitutions);  
```  
  
#### <a name="parameters"></a>Parametry  
 `templateStr`  
 Požadováno. Řetězec šablony.  
  
 `obj`  
 Požadováno. Objekt ve správném formátu zadaný notaci objekt literálu, například {nezpracovaná: 'Hodnota'}.  
  
 `...substitutions`  
 Volitelné. Pole ( [rest parametr](../../javascript/functions-javascript.md)) skládající se z jedné nebo více hodnot nahrazení.  
  
## <a name="remarks"></a>Poznámky  
 `String.raw` Funkce je určena pro použití s [řetězce šablon](../../javascript/advanced/template-strings-javascript.md). Nezpracovaný řetězec bude obsahovat žádné řídicí znaky a zpětná lomítka, které jsou k dispozici v řetězci.  
  
 Pokud je vyvolána chyba `obj` není objekt ve správném formátu.  
  
## <a name="example"></a>Příklad  
  
```  
function log(arg) {  
    if(console && console.log) {  
        console.log(arg);  
    }  
};  
  
var name = "bob";  
  
log(`hello \t${name}`);  
log(String.raw`hello \t${name}`);  
// The following usage for String.raw is supported but  
// is not typical.  
log(String.raw({ raw: 'fred'}, 'F', 'R', 'E'));  
  
// Output:  
// hello   bob  
// hello \tbob  
// fFrReEd   
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]