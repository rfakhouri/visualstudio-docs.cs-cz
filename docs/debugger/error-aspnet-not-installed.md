---
title: 'Chyba: Prostředí ASP.NET není nainstalováno | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: fd660ea2cdeaaae5d37811406221a7d150ab9bef
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056658"
---
# <a name="error-aspnet-not-installed"></a>Chyba: Prostředí ASP.NET není nainstalováno.
Tato chyba nastane, když [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] není správně nainstalován v počítači, který se pokoušíte ladění. To může znamenat, že [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] nebyl nikdy nainstalovaný nebo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] byla nainstalována jako první a služba IIS byla nainstalována později.  
  
### <a name="to-reinstall-aspnet"></a>Přeinstalujte ASP.NET  
  
1.  V okně příkazového řádku spusťte následující příkaz:  
  
    ```cmd
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     kde *verze* představuje číslo verze rozhraní .NET Framework nainstalované v počítači, například v1.0.370. Můžete určit verzi rozhraní framework podle `\WINDOWS\Microsoft.NET\Framework` adresáře.  
  
    > [!NOTE]
    >  Se systémem Windows Server 2003, můžete nainstalovat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pomocí **přidat nebo odebrat programy** v Ovládacích panelech.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
