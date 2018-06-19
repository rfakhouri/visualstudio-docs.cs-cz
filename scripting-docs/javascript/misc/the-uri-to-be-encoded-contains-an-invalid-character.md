---
title: Kódovaný identifikátor URI obsahuje neplatný znak | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5024
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a3f0fdbb-8d4b-41ae-a396-43dfc9483760
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e93d145ea6b0991123c2a7c80f8acf54a83a264
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788706"
---
# <a name="the-uri-to-be-encoded-contains-an-invalid-character"></a>Kódovaný identifikátor URI obsahuje neplatný znak
Pokoušíte se o zakódujte řetězec jako identifikátor URI (Uniform Resource Identifier), ale obsahuje neplatné znaky. I když většina znaky jsou platné uvnitř řetězců, které má být převeden na identifikátory URI, některé sekvence znaků Unicode jsou neplatné.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zkontrolujte, zda je řetězec, který má být zakódován obsahuje pouze platné kódování Unicode pořadí. Úplný identifikátor URI se skládá z posloupnost součásti a oddělovačů. Názvy v lomených závorkách představují součásti a ":", "/", ";" a "?" jsou vyhrazené znaky, které se používají jako oddělovače. Obecné formuláře je:  
  
    ```JavaScript  
    <Scheme>:<first>/<second>;<third>?<fourth>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [encodeURI – funkce](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeuricomponent – funkce](../../javascript/reference/encodeuricomponent-function-javascript.md)