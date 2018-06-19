---
title: S názvem bez přípony – příkaz (JavaScript) | Microsoft Docs
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
- labeled_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- continue statement
- labeled statement
- identifiers, statements
ms.assetid: 019f898e-9e27-4be4-a22f-c5927c7fcae2
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd72b15d3fc9083ca127a48981c0cd0a7ee56b6c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790788"
---
# <a name="labeled-statement-javascript"></a>Příkaz s popiskem (JavaScript)
Poskytuje identifikátor pro příkaz.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      label :  
   statements   
```  
  
## <a name="parameters"></a>Parametry  
 *Popisek*  
 Požadováno. Jedinečný identifikátor použité při odkazu na příkaz s popiskem.  
  
 `statements`  
 Volitelné. Jeden nebo více příkazů, které jsou přidružené k *popisek*.  
  
## <a name="remarks"></a>Poznámky  
 Popisky jsou používány **zalomení** a **pokračovat** příkazy k určení příkazu, ke kterému **zalomení** a **pokračovat** použít.  
  
## <a name="example"></a>Příklad  
 V následujícím kódu **pokračovat** příkaz odkazuje na **pro** smyčky, která předchází `Inner:` příkaz. Když `j` je 24, **pokračovat** příkaz způsobuje, **pro** přejít do další iterace smyčky. Čísla 21 až 23 a 25 prostřednictvím 30 tisku na každém řádku.  
  
```JavaScript  
Outer:  
for (i = 1; i <= 10; i++) {  
   document.write ("<br />");  
   document.write ("i: " + i);  
   document.write (" j: ");  
  
Inner:  
   for (j = 21; j <= 30; j++) {  
      if (j == 24)  
          {  
          continue Inner;  
      }  
      document.write (j + " ");  
  }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Příkaz BREAK](../../javascript/reference/break-statement-javascript.md)   
 [Continue – příkaz](../../javascript/reference/continue-statement-javascript.md)