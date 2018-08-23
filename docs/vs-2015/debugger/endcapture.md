---
title: EndCapture | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06084c3b-e065-49b6-968e-d578762fb871
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 142a2f7b43f3b0a16d4dd1d983f11b485022f43f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670081"
---
# <a name="endcapture"></a>EndCapture
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [EndCapture](https://docs.microsoft.com/visualstudio/debugger/graphics/endcapture).  
  
Končí zachycení interval, který byl spuštěn s `BeginCapture`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void EndCapture();  
```  
  
## <a name="remarks"></a>Poznámky  
 Interval sběru obvykle zahrnuje podmnožinu jeden snímek, například když budete chtít zachytit grafické informace pouze o druh volání draw. Pokud interval zachytávání zahrnuje volání k dispozici, jsou zachyceny dvěma snímky informací grafiky. První snímek zahrnuje interval mezi volání `BeginCapture` a volání k dispozici; druhý snímek zahrnuje interval mezi první události rozhraní Direct3D po volání k dispozici a volání `EndCapture`.  
  
 K zachycení intervalu, musíte připravit vaše aplikace k zachycení a zaznamenání grafických informací – to znamená, musí zavoláte [Init](../debugger/init.md) prostřednictvím instance `VsgDbg` třídy před voláním `BeginCapture` nebo `EndCapture`.  
  
## <a name="see-also"></a>Viz také  
 [BeginCapture](../debugger/begincapture.md)   
 [CaptureCurrentFrame](../debugger/capturecurrentframe.md)



