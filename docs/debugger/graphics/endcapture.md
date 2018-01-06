---
title: EndCapture | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06084c3b-e065-49b6-968e-d578762fb871
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6f717d8b1e95531f0b758a88db48b610b343ee60
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="endcapture"></a>EndCapture
Ukončí zachycení interval, který byl spuštěn s `BeginCapture`.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void EndCapture();  
```  
  
## <a name="remarks"></a>Poznámky  
 Intervalu zachycení obvykle pokrývá podmnožinu jeden rámečku, například když chcete zaznamenání grafických informací pouze o druh kreslení volání. Pokud interval zachycení zahrnuje volání k dispozici, pak dva grafických informací rámce. První snímek zahrnuje interval mezi volání `BeginCapture` a volání k dispozici; druhý rámečku zahrnuje interval mezi první událost Direct3D – po volání k dispozici a volání `EndCapture`.  
  
 K zachycení intervalu, je nutné připravit aplikace k zaznamenání a zaznamenání grafických informací – to znamená, můžete je mít volat [Init](init.md) prostřednictvím instance `VsgDbg` třídy před voláním `BeginCapture` nebo `EndCapture`.  
  
## <a name="see-also"></a>Viz také  
 [BeginCapture](begincapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)