---
title: 'Chyba: Prostředí ASP.NET není nainstalováno | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
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
ms.openlocfilehash: 41d2804ce3cab18acf697333ee9950b4717f9500
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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