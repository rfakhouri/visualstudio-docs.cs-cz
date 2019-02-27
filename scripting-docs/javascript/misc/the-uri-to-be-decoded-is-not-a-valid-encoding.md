---
title: Dekódovaný identifikátor URI nemá platné kódování | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5025
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 029e0790-ffd1-496d-8700-3b3dbac1b6fd
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 792403a9a53f11431e87115d7a95345e316dc2ac
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56844292"
---
# <a name="the-uri-to-be-decoded-is-not-a-valid-encoding"></a>Dekódovaný identifikátor URI nemá platné kódování
Pokoušíte se o dekódování nesprávně formátovaný URI (Uniform Resource Identifier). Identifikátory URI mají zvláštní syntaxi; Většina jiných než alfanumerických znaků musí kódováním předtím, než je možné v identifikátoru URI. Můžete použít `encodeURI` a `encodeURIComponent` metody vytvořit identifikátor URI z normální [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] řetězec.  
  
 Úplný identifikátor URI se skládá z pořadí komponent a oddělovače. Obecný formát je následující:  
  
```JavaScript  
<Scheme>:<first>/<second>;<third>?<fourth>  
```  
  
 Názvy v lomených závorkách představují součásti a ":", "/", ";" a "?" jsou vyhrazené znaky, které jsou použity jako oddělovače.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Ujistěte se, že se pokoušíte dekódování jenom platné identifikátory URI. Nelze dekódovat normální [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] řetězce mohou obsahovat neplatné znaky.  
  
## <a name="see-also"></a>Viz také  
 [decodeURI – funkce](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent – funkce](../../javascript/reference/decodeuricomponent-function-javascript.md)