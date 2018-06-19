---
title: name – vlastnost (chyba) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- name
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Name property
- name property, error name
ms.assetid: 94df2d6b-f1a1-4931-a956-0a930cb87f76
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1a12157b4c467499fab23f7c4cb1be91e9ac5440
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791766"
---
# <a name="name-property-error-javascript"></a>name – vlastnost (Chyba) (JavaScript)
Vrací název chybu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
errorObj.  
name  
  
```  
  
## <a name="parameters"></a>Parametry  
 `errorObj`  
 Požadováno. Instance `Error` objektu.  
  
## <a name="remarks"></a>Poznámky  
 **Název** vlastnost vrací typ název nebo výjimky k chybě. Když dojde k chybě za běhu, je název vlastnost nastavena na jednu z následujících typů nativní výjimka:  
  
|Typ výjimky|Význam|  
|--------------------|-------------|  
|ConversionError –|K této chybě dojde, kdykoli dojde k pokusu o převedení objektu na něco jiného, ke kterému nelze převést.|  
|RangeError –|K této chybě dojde, když funkce se dodává s argumentem překročil jeho rozsah povolených hodnot. Například tato chyba nastane, pokud se pokusíte sestavit `Array` objektu s délkou, která není platné kladné celé číslo.|  
|ReferenceError –|K této chybě dojde, pokud byl zjištěn neplatný odkaz. Tato chyba nastane například, pokud je očekávaný odkaz `null`.|  
|RegExpError –|K této chybě dojde, když dojde k chybě kompilace s regulárním výrazem. Po regulární výraz je kompilovat, ale k této chybě nemůže dojít. V tomto příkladu se stane, například při regulární výraz je deklarovaný s vzor, který obsahuje neplatnou syntaxi nebo jiné než flags **i**, **g**, nebo **m**, nebo obsahuje stejné příznak více než jednou.|  
|Chyba syntaxe|K této chybě dojde, když je analyzován zdrojový text a že zdrojový text nedodrží správnou syntaxi. Tato chyba nastane, například v případě `eval` funkce je volána s argumentem, který není platný program text.|  
|TypeError|K této chybě dojde, vždy, když skutečný typ operandu neodpovídá očekávanému typu. Příklad při výskytu této chyby je provedené na něco volání funkce, která není objekt nebo nepodporuje volání.|  
|URIError –|K této chybě dojde, když je zjištěna k neplatný ukazatel URI (Uniform Resource). To je třeba chyba nastane, když se najde neplatný znak v řetězci, který je kódovaný nebo dekódovat.|  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu způsobí výjimku TypeError vyvolání a zobrazí název chyba a jeho zprávu.  
  
```JavaScript  
try  
{  
    var x = y;  
}  
catch(e)  
{  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
```  
  
## <a name="example"></a>Příklad  
 Výstup tohoto kódu je následující.  
  
```JavaScript  
Error Message: 'y' is undefined  
Error Code: 5009  
Error Name: TypeError  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [Error – objekt](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Description – vlastnost (chyba)](../../javascript/reference/description-property-error-javascript.md)   
 [Message – vlastnost (chyba)](../../javascript/reference/message-property-error-javascript.md)   
 [Number – vlastnost (chyba)](../../javascript/reference/number-property-error-javascript.md)