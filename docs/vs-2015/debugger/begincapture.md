---
title: BeginCapture | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2f9bc573799ddb5fdd094c7c0e571a88c13b5420
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627433"
---
# <a name="begincapture"></a>BeginCapture
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [BeginCapture](https://docs.microsoft.com/visualstudio/debugger/graphics/begincapture).  
  
Začne sběr intervalu, který bude končit `EndCapture`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void BeginCapture();  
```  
  
## <a name="remarks"></a>Poznámky  
 Interval sběru obvykle zahrnuje podmnožinu jeden snímek, například když budete chtít zachytit grafické informace pouze o druh volání draw. Pokud interval zachytávání zahrnuje volání k dispozici, jsou zachyceny dvěma snímky informací grafiky. První snímek zahrnuje interval mezi volání `BeginCapture` a volání k dispozici; druhý snímek zahrnuje interval mezi první události rozhraní Direct3D po volání k dispozici a volání `EndCapture`.  
  
 K zachycení intervalu, musíte připravit vaše aplikace k zachycení a zaznamenání grafických informací – to znamená, musí zavoláte [Init](../debugger/init.md) prostřednictvím instance `VsgDbg` třídy před voláním `BeginCapture` nebo `EndCapture`.  
  
## <a name="see-also"></a>Viz také  
 [EndCapture](../debugger/endcapture.md)   
 [CaptureCurrentFrame](../debugger/capturecurrentframe.md)



