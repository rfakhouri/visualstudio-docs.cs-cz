---
title: EndCapture | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 06084c3b-e065-49b6-968e-d578762fb871
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e8f72e3bcd3755fe59af5207586cf9cf03d432f4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54967622"
---
# <a name="endcapture"></a>EndCapture
Končí zachycení interval, který byl spuštěn s `BeginCapture`.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void EndCapture();  
```  
  
## <a name="remarks"></a>Poznámky  
 Interval sběru obvykle zahrnuje podmnožinu jeden snímek, například když budete chtít zachytit grafické informace pouze o druh volání draw. Pokud interval zachytávání zahrnuje volání k dispozici, jsou zachyceny dvěma snímky informací grafiky. První snímek zahrnuje interval mezi volání `BeginCapture` a volání k dispozici; druhý snímek zahrnuje interval mezi první události rozhraní Direct3D po volání k dispozici a volání `EndCapture`.  
  
 K zachycení intervalu, musíte připravit vaše aplikace k zachycení a zaznamenání grafických informací – to znamená, musí zavoláte [Init](init.md) prostřednictvím instance `VsgDbg` třídy před voláním `BeginCapture` nebo `EndCapture`.  
  
## <a name="see-also"></a>Viz také  
 [BeginCapture](begincapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)