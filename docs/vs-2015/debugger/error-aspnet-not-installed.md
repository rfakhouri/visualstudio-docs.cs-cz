---
title: 'Chyba: Prostředí ASP.NET není nainstalováno | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.http_not_supported
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
ms.assetid: 6286dd3d-3e2b-4edd-959d-81e0ed45500b
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 35268c6867c5438f2f3d0c4c4f9e649451a21991
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49220971"
---
# <a name="error-aspnet-not-installed"></a>Chyba: Prostředí ASP.NET není nainstalováno.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

K této chybě dochází při [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] není správně nainstalován v počítači, který se pokoušíte ladit. To může znamenat, že [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] nebyl nikdy nainstalován nebo které [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] byla nainstalovaná jako první a služby IIS byl nainstalován později.  
  
### <a name="to-reinstall-aspnet"></a>K opětovné instalaci technologie ASP.NET  
  
1.  Z okna příkazového řádku spusťte následující příkaz:  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     kde *verze* představuje číslo verze rozhraní .NET Framework nainstalované v počítači, jako je například v1.0.370. Můžete určit verzi rozhraní framework hledání `\WINDOWS\Microsoft.NET\Framework` adresáře.  
  
    > [!NOTE]
    >  Se systémem Windows Server 2003, můžete nainstalovat [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pomocí **přidat nebo odebrat programy** v Ovládacích panelech.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



