---
title: CaptureCurrentFrame | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2fcb05d63370f8f40ab09f0978e0f49dbe7d6a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671599"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CaptureCurrentFrame](https://docs.microsoft.com/visualstudio/debugger/graphics/capturecurrentframe).  
  
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



