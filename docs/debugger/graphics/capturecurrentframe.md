---
title: CaptureCurrentFrame | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 739f2a9a97fefcb1bc57c7987d5afec7a09ff4ad
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
Zaznamená zbytek aktuální rámec grafiky souboru protokolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>Poznámky  
 Pokud aktuálně probíhá jiná zachycení – například zachycení, která byla spuštěna `BeginCapture` funkce – tento snímek je dokončena a zaznamenány do protokolu grafiky jako odlišné rámce. Okamžitě diagnostiky grafiky později, začne zaznamenávání zbytek aktuální rámce, který je taky zaznamená jako odlišné rámce. Aktuální snímek end je označena kvalifikátorem volání k dispozici.  
  
 Když Pokud chcete zachytit snímek, je nutné připravit aplikace k zaznamenání a zaznamenání grafických informací – tedy můžete musí mít volána [Init](init.md) prostřednictvím instance `VsgDbg` třídy před voláním `CaptureCurrentFrame`.  
  
## <a name="see-also"></a>Viz také  
 [Init –](init.md)   
 [BeginCapture](begincapture.md)