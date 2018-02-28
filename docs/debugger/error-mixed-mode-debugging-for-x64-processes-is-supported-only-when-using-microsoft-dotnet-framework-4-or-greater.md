---
title: "Chyba: Ve smíšeném režimu ladění pro x64 procesy se podporuje jenom při použití rozhraní Microsoft .NET Framework 4 nebo vyšší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 87ca4ffe1a80d6d6fdc948c3a1617f888aba4baf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>Chyba: Ladění ve smíšeném režimu pro procesy x64 je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 4 nebo vyšší.
Chcete-li ladit smíšený nativního a spravovaného kódu v procesu 64-bit, musíte mít [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze 4. Ladění ve smíšeném režimu 64bitové procesy s [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze starší než 4 není podporováno.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Proveďte jeden z následujících kroků:  
  
    -   Upgrade vašeho [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] do verze 4.  
  
    -   Sestavení 32bitová verze aplikace pro ladění.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)