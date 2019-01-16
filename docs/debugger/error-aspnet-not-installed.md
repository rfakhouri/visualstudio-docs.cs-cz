---
title: 'Chyba: Prostředí ASP.NET není nainstalováno | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.http_not_supported
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 41ec708b25bc74eb1f566981ee4bbcdc23827087
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "53902106"
---
# <a name="error-aspnet-not-installed"></a>Chyba: Prostředí ASP.NET není nainstalováno
K této chybě dochází při [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] není správně nainstalován v počítači, který se pokoušíte ladit. To může znamenat, že [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] nebyl nikdy nainstalován nebo které [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] byla nainstalovaná jako první a služby IIS byl nainstalován později.  
  
### <a name="to-reinstall-aspnet"></a>K opětovné instalaci technologie ASP.NET  
  
1. Z okna příkazového řádku spusťte následující příkaz:  
  
   ```cmd
   \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
   ```  
  
    kde *verze* představuje číslo verze rozhraní .NET Framework nainstalované v počítači, jako je například v1.0.370. Můžete určit verzi rozhraní framework hledání `\WINDOWS\Microsoft.NET\Framework` adresáře.  
  
   > [!NOTE]
   >  Se systémem Windows Server 2003, můžete nainstalovat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pomocí **přidat nebo odebrat programy** v Ovládacích panelech.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
