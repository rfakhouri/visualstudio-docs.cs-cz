---
title: BeginCapture | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a93eb940e848767412b87509ed5f9e8845afdb66
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="begincapture"></a>BeginCapture
Zahájí zachycení interval, který bude končit `EndCapture`.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void BeginCapture();  
```  
  
## <a name="remarks"></a>Poznámky  
 Intervalu zachycení obvykle pokrývá podmnožinu jeden rámečku, například když chcete zaznamenání grafických informací pouze o druh kreslení volání. Pokud interval zachycení zahrnuje volání k dispozici, pak dva grafických informací rámce. První snímek zahrnuje interval mezi volání `BeginCapture` a volání k dispozici; druhý rámečku zahrnuje interval mezi první událost Direct3D – po volání k dispozici a volání `EndCapture`.  
  
 K zachycení intervalu, je nutné připravit aplikace k zaznamenání a zaznamenání grafických informací – to znamená, můžete je mít volat [Init](init.md) prostřednictvím instance `VsgDbg` třídy před voláním `BeginCapture` nebo `EndCapture`.  
  
## <a name="see-also"></a>Viz také  
 [EndCapture](endcapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)