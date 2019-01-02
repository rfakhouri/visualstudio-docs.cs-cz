---
title: Idiaenumsegments::clone – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Clone method
ms.assetid: 93deaac6-72ab-4408-ba14-66174a618757
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de7b9b12c17f6a0d9295809551d403b4d490dd94
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859091"
---
# <a name="idiaenumsegmentsclone"></a>IDiaEnumSegments::Clone
Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Clone (   
   IDiaEnumSegments** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppenum  
 [out] Vrátí [idiaenumsegments –](../../debugger/debug-interface-access/idiaenumsegments.md) objekt, který obsahuje duplicitní čítače výčtu. Segmenty nejsou duplicitní, pouze enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)