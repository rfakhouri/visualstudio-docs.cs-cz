---
title: BeginCapture | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b16fdc4d0a12d7082400e697ca44a7ca4c549f9a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62431794"
---
# <a name="begincapture"></a>BeginCapture
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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
