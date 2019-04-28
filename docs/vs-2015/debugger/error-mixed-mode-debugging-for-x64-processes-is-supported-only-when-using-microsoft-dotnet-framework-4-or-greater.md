---
title: 'Chyba: Ve smíšeném režimu ladění pro x64 procesy se podporuje jenom při použití rozhraní Microsoft .NET Framework 4 nebo vyšší | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e4b0216c-7006-4832-883f-08e982ba8d3f
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 56ae0260b73d41e953fa25b74eae9b012604258a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62535486"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>Chyba: Ladění ve smíšeném režimu pro procesy x64 je podporované, jenom pokud používáte rozhraní Microsoft .NET Framework 4 nebo vyšší.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chcete-li ladit smíšené nativního a spravovaného kódu do 64bitového procesu, musíte mít [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] verze 4. Kombinovaný režim ladění 64bitových procesů s [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] verze starší než 4 není podporováno.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Proveďte jeden z následujících kroků:  
  
    - Upgrade vašeho [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] na verzi 4.  
  
    - Sestavení 32bitové verze ladění vaší aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)
