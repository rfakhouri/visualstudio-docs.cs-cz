---
title: "Chyba: Prostředí ASP.NET není nainstalováno | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.http_not_supported
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
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: aspnet
ms.openlocfilehash: 36930db142821b11ed83edf846ccd3f65fd81d1d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-aspnet-not-installed"></a>Chyba: Prostředí ASP.NET není nainstalováno.
Tato chyba nastane, když [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] není správně nainstalován v počítači, který se pokoušíte ladění. To může znamenat, že [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] nebyl nikdy nainstalovaný nebo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] byla nainstalována jako první a služba IIS byla nainstalována později.  
  
### <a name="to-reinstall-aspnet"></a>Přeinstalujte ASP.NET  
  
1.  V okně příkazového řádku spusťte následující příkaz:  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     kde *verze* představuje číslo verze rozhraní .NET Framework nainstalované v počítači, například v1.0.370. Můžete určit verzi rozhraní framework podle `\WINDOWS\Microsoft.NET\Framework` adresáře.  
  
    > [!NOTE]
    >  Se systémem Windows Server 2003, můžete nainstalovat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pomocí **přidat nebo odebrat programy** v Ovládacích panelech.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)