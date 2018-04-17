---
title: VsgDbg::VsgDbg (konstruktor) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 670651e6-5e79-4845-b0c2-671beb7055a8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 336fd55ddd4cd85daed7cebc9cadab321b50c189
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vsgdbgvsgdbg-constructor"></a>VsgDbg::VsgDbg (konstruktor)
Vytvoří instanci objektu `VsgDbg` třídy s nebo bez Příprava v aplikaci součást diagnostiky grafiky aktivně zaznamenání a zaznamenání grafických informací ve výchozím nastavení, na základě zadaného parametru logická hodnota.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
VsgDbg(  
  bDefaultInit  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bDefaultInit`  
 `true` k určení, že je v aplikaci součást diagnostiky grafiky jako připravené k aktivně zachycení a zaznamenání grafických informací; `false` k určení, že aplikace nesmí připravte se na aktivním zachycení a zaznamenání grafických informací v tuto chvíli.  
  
## <a name="remarks"></a>Poznámky  
 Při volání konstruktoru s `bDefaultInit` nastavena na `true`, název souboru souboru protokolu grafika je dáno jak `DONT_SAVE_VSGLOG_TO_TEMP` a `VSG_DEFAULT_RUN_FILENAME` preprocesoru značky jsou definovány před `vsgcapture.h` je součástí vaší aplikace.  
  
 Při volání konstruktoru s `bDefaultInit` nastavena na `false`, v aplikaci součást diagnostiky grafiky mohly být připraveny aktivně zaznamenání a zaznamenání grafických informací později při volání `Init` funkce.  
  
## <a name="see-also"></a>Viz také  
 [VsgDbg:: ~ VsgDbg (destruktor)](vsgdbg-tilde-vsgdbg-destructor.md)   
 [Init –](init.md)   
 [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)   
 [VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)