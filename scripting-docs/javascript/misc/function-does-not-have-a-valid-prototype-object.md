---
title: Funkce nemá platný prototyp objektu | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b9e34652-190f-4b57-b253-df2e8c4d09c6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 413f73a53a6d4f698219139a87c449be4c155831
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63007500"
---
# <a name="function-does-not-have-a-valid-prototype-object"></a>Metoda nemá platný prototyp objektu.
Pokusili jste se použít **instanceof** k určení, pokud byl objekt odvozené od třídy určitou funkci, ale předefinovat objektu `prototype` vlastnost jako buď `null`, nebo externí typ objektu, který (obě neplatné [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty). Externí objekt může být objektu v objektovém modelu hostitele (například aplikace Internet Explorer dokumentu nebo objektu window), nebo externí objekt modelu COM.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Zajištění funkce `prototype` vlastnost odkazuje na platnou [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objektu.  
  
## <a name="see-also"></a>Viz také  
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [prototype – vlastnost (Object)](../../javascript/reference/prototype-property-object-javascript.md)