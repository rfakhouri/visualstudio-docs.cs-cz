---
title: CaptureCurrentFrame | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2718e800e2a31eb66319259ed1e43f2ab8b084c5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54754924"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zaznamená zbytek aktuálního snímku do souboru protokolu grafiky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>Poznámky  
 Pokud právě probíhá jiné sběrného – například zachycení, kterou zahájil `BeginCapture` funkce – zachycení je dokončena a zaznamenána do protokolu grafiky jako odlišné rámce. Okamžitě diagnostiky grafiky později, začne zachytávání zbytek aktuální rámec, která je také zaznamenána jako odlišné rámce. Konec aktuálního snímku je označen volání k dispozici.  
  
 K zachycení snímku, musíte připravit aplikaci tak, aby zachycení a zaznamenání informací grafiky – to znamená, musí zavoláte [Init](../debugger/init.md) prostřednictvím instance `VsgDbg` třídy před voláním `CaptureCurrentFrame`.  
  
## <a name="see-also"></a>Viz také  
 [Inicializace](../debugger/init.md)   
 [BeginCapture](../debugger/begincapture.md)
