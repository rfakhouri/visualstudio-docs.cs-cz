---
title: Délce pole musí být přiřazeno konečné kladné číslo | Dokumentace společnosti Microsoft
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
- VS.WebClient.Help.SCRIPT5030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c51c66a4-a543-4e95-b18d-2cfbcb3d1fdd
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63a9d714173334192028b9096de41968befa85ef
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348695"
---
# <a name="array-length-must-be-assigned-a-finite-positive-number"></a>Délce pole musí být přiřazeno konečné kladné číslo.
Při nastavení **délka** vlastnosti existujícího **pole** objektu, jste zadali délka pole, která nebyla kladné číslo nebo nula. K této chybě dochází, když přiřadíte hodnotu, která **délka** vlastnost `Array` objekt, který je záporný nebo nečíselné (`NaN`). Všimněte si, že [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] automaticky převede desetinná čísla na celý celých čísel.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Vlastnost length přiřadíte kladné celé číslo. Neexistuje žádná horní mez pro velikost pole, než je maximální celočíselnou hodnotu (přibližně 4 miliardy). Následující příklad ukazuje správný způsob, jak nastavit **délka** vlastnost **pole** objektu.  
  
    ```JavaScript  
    var my_array = new Array();  
    my_array.length = 99;  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Používání polí](../../javascript/advanced/using-arrays-javascript.md)