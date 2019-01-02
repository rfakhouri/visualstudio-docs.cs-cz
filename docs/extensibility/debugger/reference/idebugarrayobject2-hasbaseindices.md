---
title: IDebugArrayObject2::HasBaseIndices | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- HasBaseIndices
- IDebugArrayObject2::HasBaseIndices
ms.assetid: 51a5d145-ea53-422c-b5cf-c800cf64b8e6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3cb53ba84d73348f110154a478c772b07cefd329
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53857316"
---
# <a name="idebugarrayobject2hasbaseindices"></a>IDebugArrayObject2::HasBaseIndices
Určuje, zda pole má základní indexy (dolní mez).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT HasBaseIndices (  
   BOOL* pfHasBaseIndices  
);  
```  
  
```csharp  
int HasBaseIndices (  
   out bool pfHasBaseIndices  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pfHasBaseIndices`  
 [out] TRUE, pokud chcete určit, že pole má základní indexy (dolní meze); v opačném případě hodnota FALSE.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.