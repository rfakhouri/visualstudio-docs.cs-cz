---
title: Řetězce šablon (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2e525a5-b0fc-49c3-95a0-641788e5c12a
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7b6aa430fd4f958c5519093b85d399060b6031a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788784"
---
# <a name="template-strings-javascript"></a>Řetězce šablon (JavaScript)
V [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)], řetězce šablon můžete použít k vytvoření textové literály s vložené výrazy. Řetězce šablon poskytují integrovanou podporu pro více řádků řetězce.  
  
 Chcete-li vytvořit řetězec šablony, použijte čárka (také nazývané back značek) ('), uzavřete řetězec místo jednoduchých nebo dvojitých uvozovek. Následující příklad kódu ukazuje řetězec jednoduchého šablony.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Řetězce šablon může zahrnovat zalomení řádku bez nutnosti použití znaku konce řádku (\n).  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Znak $ slouží k určení zástupné symboly v rámci řetězec šablony. Syntaxe je ${*výraz*}, kde *výraz* je jakýkoli JavaScript výraz například proměnné nebo funkce, jak je znázorněno v následujícím příkladu.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Funkce s příznakem šablon, které umožňují změnit hodnotu řetězce šablony pomocí funkce, která je volána s argumenty z řetězce šablony. První argument je pole textové literály, oddělená výrazů řetězec šablony, které obsahuje, a druhý argument je pole ( [Rest parametr](../../javascript/functions-javascript.md)) s hodnotami výrazů řetězec šablony.  
  
 V následujícím příkladu, funkce s příznakem šablony, buildURL slouží k vytvoření adresy URL. Syntaxe je pro použití názvu funkce hned následuje řetězec šablony.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 Pokud budete potřebovat přístup k hodnotám Nezpracovaný řetězec předaná, první argument předaný podporuje funkce s příznakem šablony `raw` vlastnost, která vrací Nezpracovaný řetězec formátu předaná řetězce.  
  
```  
function buildURL(strArray, ...valArray) {  
    console.log(strArray.raw);  
}  
  
var lang = "en-us";  
var a = "library";  
var b = "dn771551.aspx";  
  
// Call the tagged template function.  
var url = buildURL`http://msdn.microsoft.com/${lang}/${a}/${b}`;  
  
// Ouput:  
// http://msdn.microsoft.com/  
// /  
// en-us  
// library  
```  
  
> [!NOTE]
>  Můžete také [String.RAW –](../../javascript/reference/string-raw-function-javascript.md) funkci vrátíte Nezpracovaný řetězec formátu řetězec šablony.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace jazyka JavaScript](../../javascript/javascript-language-reference.md)   
 [Pokročilý JavaScript](../../javascript/advanced/advanced-javascript.md)