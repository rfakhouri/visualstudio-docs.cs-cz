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
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 98db3475c7d83427eb516f696731a738e34bd7a1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399280"
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
   > Se systémem Windows Server 2003, můžete nainstalovat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pomocí **přidat nebo odebrat programy** v Ovládacích panelech.

## <a name="see-also"></a>Viz také
- [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
