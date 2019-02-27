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
ms.openlocfilehash: 31226f972ff4714dd81207cf27d862d3449184a5
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840760"
---
# <a name="function-does-not-have-a-valid-prototype-object"></a>Metoda nemá platný prototyp objektu.
Pokusili jste se použít **instanceof** k určení, pokud byl objekt odvozené od třídy určitou funkci, ale předefinovat objektu `prototype` vlastnost jako buď `null`, nebo externí typ objektu, který (obě neplatné [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty). Externí objekt může být objektu v objektovém modelu hostitele (například aplikace Internet Explorer dokumentu nebo objektu window), nebo externí objekt modelu COM.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zajištění funkce `prototype` vlastnost odkazuje na platnou [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objektu.  
  
## <a name="see-also"></a>Viz také  
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [prototype – vlastnost (Object)](../../javascript/reference/prototype-property-object-javascript.md)