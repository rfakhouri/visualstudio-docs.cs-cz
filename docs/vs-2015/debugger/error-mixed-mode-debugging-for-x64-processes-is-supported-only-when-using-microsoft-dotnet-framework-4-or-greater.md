---
title: 'Chyba: Ve smíšeném režimu ladění pro x64 procesy se podporuje jenom při použití rozhraní Microsoft .NET Framework 4 nebo vyšší. | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e4b0216c-7006-4832-883f-08e982ba8d3f
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 479a771300e37e09412accb16771d31454469f95
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668574"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>Chyba: Ladění ve smíšeném režimu pro procesy x64 je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 4 nebo vyšší.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: pracující v kombinovaném režimu ladění pro x64 procesy se podporuje jenom při použití rozhraní Microsoft .NET Framework 4 nebo vyšší](https://docs.microsoft.com/visualstudio/debugger/error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-dotnet-framework-4-or-greater).  
  
Chcete-li ladit smíšené nativního a spravovaného kódu do 64bitového procesu, musíte mít [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] verze 4. Kombinovaný režim ladění 64bitových procesů s [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] verze starší než 4 není podporováno.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Proveďte jeden z následujících kroků:  
  
    -   Upgrade vašeho [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] na verzi 4.  
  
    -   Sestavení 32bitové verze ladění vaší aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



