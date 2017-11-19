---
title: "Komentář příkazy (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Comment_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- comments, ignoring
- comment statements
ms.assetid: b604824f-ac17-49d3-bcdb-2a893ab5fff8
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c270379725550e116928bbecd69e6be51c34992f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="comment-statements-javascript"></a>Příkazy komentářů (JavaScript)
Způsobí, že komentáře, který se má ignorovat pomocí [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] analyzátor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Single-line Comment:  
// comment   
```  
  
```  
Multiline Comment:  
/*  
comment  
*/  
```  
  
```  
Comments with conditional compilation:  
//@CondStatement   
  
/*@  
condStatement  
@*/  
```  
  
## <a name="remarks"></a>Poznámky  
 `comment` Argument je text jakékoli komentáře, které chcete zahrnout do vašeho skriptu. `condStatement` Argument má být použita, pokud je aktivovaná Podmíněná kompilace. Pokud se používají jeden řádek komentáře, může být bez mezer "/ /" a "@" znaků.  
  
 Použití komentáře k udržování částí skriptu před čtením [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] analyzátor. Komentáře můžete zahrnout vysvětlující poznámky v programu.  
  
 Pokud se používají jeden řádek komentáře, ignoruje analyzátor textu mezi značky poznámky a konec řádku. Pokud se používají Víceřádkový komentáře, ignoruje analyzátor textu mezi značky začátek a konec.  
  
 Komentáře slouží k podpoře Podmíněná kompilace při zachování kompatibility s prohlížeči, které tuto funkci nepodporují. Tyto prohlížeče považují tyto formuláře jako jeden řádek komentáře nebo poznámky Víceřádkový v uvedeném pořadí.  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje nejběžnější použití komentáře.  
  
```JavaScript  
/* This is a multiline comment that  
    can span as many lines as necessary.  */  
function myfunction(arg1, arg2){  
    var r;  
    // This is a single line comment.  
    r = arg1 + arg2  
    return(r);  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat Podmíněná kompilace. Tento příklad používá oddělovače speciální komentáře, které se používají pouze v případě, že je aktivován Podmíněná kompilace `@cc_on` příkaz. Skriptovací jádra, která nepodporují podmíněnou kompilaci, vidí pouze zprávu, že podmíněná kompilace není podporována.  
  
```JavaScript  
/*@cc_on @*/  
/*@if (@_jscript_version >= 4)  
    alert("JavaScript version 4 or better");  
    @else @*/  
    alert("Conditional compilation not supported by this scripting engine.");  
/*@end @*/  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]