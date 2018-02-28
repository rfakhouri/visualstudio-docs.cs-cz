---
title: "Dekódovaný identifikátor URI nemá platné kódování | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5025
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 029e0790-ffd1-496d-8700-3b3dbac1b6fd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d37ca55dfd701aaeba2af729511a5ae6a4fa5f4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="the-uri-to-be-decoded-is-not-a-valid-encoding"></a>Dekódovaný identifikátor URI nemá platné kódování
Pokoušíte se o dekódovat nesprávně utvořenou identifikátor URI (Uniform Resource Identifier). Identifikátory URI mít speciální syntaxe; Většina jiných než alfanumerických znaků, musí být kódovaný před použitím v identifikátoru URI. Můžete použít `encodeURI` a `encodeURIComponent` metody k vytvoření adresu URI z něj normální [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] řetězec.  
  
 Úplný identifikátor URI se skládá z posloupnost součásti a oddělovačů. Obecné formuláře je:  
  
```JavaScript  
<Scheme>:<first>/<second>;<third>?<fourth>  
```  
  
 Názvy v lomených závorkách představují součásti a ":", "/", ";" a "?" jsou vyhrazené znaky, které se používají jako oddělovače.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zkontrolujte, zda že chcete dekódovat pouze platné identifikátory URI. Nelze dekódovat normální [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] řetězce mohou obsahovat neplatné znaky.  
  
## <a name="see-also"></a>Viz také  
 [decodeURI – funkce](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeuricomponent – funkce](../../javascript/reference/decodeuricomponent-function-javascript.md)