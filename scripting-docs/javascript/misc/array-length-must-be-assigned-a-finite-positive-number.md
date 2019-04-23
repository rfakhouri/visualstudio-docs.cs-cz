---
title: Délce pole musí být přiřazeno konečné kladné číslo | Dokumentace společnosti Microsoft
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 39f2720efbcd8defffb9d0c77047a50e57939e95
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60082344"
---
# <a name="array-length-must-be-assigned-a-finite-positive-number"></a>Délce pole musí být přiřazeno konečné kladné číslo.
Při nastavení **délka** vlastnosti existujícího **pole** objektu, jste zadali délka pole, která nebyla kladné číslo nebo nula. K této chybě dochází, když přiřadíte hodnotu, která **délka** vlastnost `Array` objekt, který je záporný nebo nečíselné (`NaN`). Všimněte si, že [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] automaticky převede desetinná čísla na celý celých čísel.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Vlastnost length přiřadíte kladné celé číslo. Neexistuje žádná horní mez pro velikost pole, než je maximální celočíselnou hodnotu (přibližně 4 miliardy). Následující příklad ukazuje správný způsob, jak nastavit **délka** vlastnost **pole** objektu.  
  
    ```JavaScript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Používání polí](../../javascript/advanced/using-arrays-javascript.md)