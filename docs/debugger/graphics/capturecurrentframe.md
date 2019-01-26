---
title: CaptureCurrentFrame | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 05d93e4cee3fb4969b928caa3ae76112708469f1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997231"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
Zaznamená zbytek aktuálního snímku do souboru protokolu grafiky.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>Poznámky  
 Pokud právě probíhá jiné sběrného – například zachycení, kterou zahájil `BeginCapture` funkce – zachycení je dokončena a zaznamenána do protokolu grafiky jako odlišné rámce. Okamžitě diagnostiky grafiky později, začne zachytávání zbytek aktuální rámec, která je také zaznamenána jako odlišné rámce. Konec aktuálního snímku je označen volání k dispozici.  
  
 K zachycení snímku, musíte připravit aplikaci tak, aby zachycení a zaznamenání informací grafiky – to znamená, musí zavoláte [Init](init.md) prostřednictvím instance `VsgDbg` třídy před voláním `CaptureCurrentFrame`.  
  
## <a name="see-also"></a>Viz také  
 [Inicializace](init.md)   
 [BeginCapture](begincapture.md)