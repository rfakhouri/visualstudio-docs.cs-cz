---
title: Funkce nemá platný prototyp objektu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b9e34652-190f-4b57-b253-df2e8c4d09c6
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4e2cbf198a452cd61f1355682ea3041436d2a27
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346693"
---
# <a name="function-does-not-have-a-valid-prototype-object"></a>Metoda nemá platný prototyp objektu.
Pokusili jste se použít **instanceof** k určení, pokud byl objekt odvozené od třídy určitou funkci, ale předefinovat objektu `prototype` vlastnost jako buď `null`, nebo externí typ objektu, který (obě neplatné [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty). Externí objekt může být objektu v objektovém modelu hostitele (například aplikace Internet Explorer dokumentu nebo objektu window), nebo externí objekt modelu COM.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zajištění funkce `prototype` vlastnost odkazuje na platnou [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objektu.  
  
## <a name="see-also"></a>Viz také  
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [prototype – vlastnost (Object)](../../javascript/reference/prototype-property-object-javascript.md)