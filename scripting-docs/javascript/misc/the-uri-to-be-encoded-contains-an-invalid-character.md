---
title: Kódovaný identifikátor URI obsahuje neplatný znak | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5024
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a3f0fdbb-8d4b-41ae-a396-43dfc9483760
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2f9111acf656bf882a3d506fe95b8361f3693ff
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63006205"
---
# <a name="the-uri-to-be-encoded-contains-an-invalid-character"></a>Kódovaný identifikátor URI obsahuje neplatný znak
Pokusili jste se kódování řetězec jako identifikátor URI (Uniform Resource Identifier), ale obsahuje neplatné znaky. I když většina znaky uvnitř řetězců, které má být převeden na identifikátory URI platný, některé sekvence znaků Unicode jsou neplatné.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Zkontrolujte, jestli řetězec, který má být zakódován obsahuje pouze platné sekvence Unicode. Úplný identifikátor URI se skládá z pořadí komponent a oddělovače. Názvy v lomených závorkách představují součásti a ":", "/", ";" a "?" jsou vyhrazené znaky, které jsou použity jako oddělovače. Obecný formát je následující:  
  
    ```JavaScript  
    <Scheme>:<first>/<second>;<third>?<fourth>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [encodeURI Function](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeURIComponent – funkce](../../javascript/reference/encodeuricomponent-function-javascript.md)