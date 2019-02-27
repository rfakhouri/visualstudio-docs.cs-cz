---
title: "'Break' nemůže být uveden mimo smyčku | Dokumentace Microsoftu"
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 11d02172-2a78-4705-a730-d21111db5f42
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 36551a1a70973409768b7971545c783b3621ffb6
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56839890"
---
# <a name="cant-have-break-outside-of-loop"></a>Příkaz 'break' nemůže být uveden mimo smyčku
Pokusili jste se použít **přerušení** – klíčové slovo mimo smyčku. **Přerušení** – klíčové slovo se používá k ukončení smyčky nebo `switch` příkazu. Musí být vložen do těla smyčky nebo `switch` příkazu. Nicméně **popisek** můžete postupovat podle break – klíčové slovo.  
  
```js
break labelname;  
```  
  
 Potřebujete jenom s popiskem formu **přerušení** – klíčové slovo při použití vnořených smyčky nebo `switch` příkazy a nutnosti přerušit ze smyčky, která není té nejvíce uvnitř.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Ujistěte se, **přerušení** – klíčové slovo se zobrazí uvnitř příkazu nadřazené smyčky nebo přepínače.  
  
## <a name="see-also"></a>Viz také  
 [BREAK – příkaz](../../javascript/reference/break-statement-javascript.md)   
 [Řízení toku programu](../../javascript/controlling-program-flow-javascript.md)   
 [Řešení potíží se skripty](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)