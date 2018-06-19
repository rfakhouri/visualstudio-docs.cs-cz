---
title: 'Chyba: Kontrola zabezpečení selhala, protože správce služby IIS neodpověděla. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.iis_not_responding
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a3b0b3412c450976cb15211813de32ab6e78eaa9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31471109"
---
# <a name="error-a-security-check-failed-because-the-iis-admin-service-did-not-respond"></a>Chyba: Kontrola zabezpečení selhala, protože služba správy služby IIS neodpověděla.
K této chybě dojde, když správce služby IIS neodpovídá. To obvykle znamená, že dojde k problému s instalací služby IIS. Nejprve ověří, zda je spuštěna služba pomocí **služby** nástroje z **nástroje pro správu**.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Znovu nainstalujte službu IIS, pomocí **přidat nebo odebrat programy** ovládací panely.  
  
-   -nebo-  
  
-   Odeberte služby IIS z počítače, pomocí ovládacího panelu Přidat nebo odebrat programy. Pokud jste odstranili služby IIS a stále máte problémy, zjistěte v registru a ujistěte se, že tento klíč již existuje:  
  
    ```  
    HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}  
    ```  
  
     -nebo-  
  
-   Zakážete službu Správce služby IIS, pomocí ovládacího panelu Nástroje pro správu. Tato akce zakáže služby IIS na počítači.  
  
     Po provedení některé z těchto tří kroků, restartujte svůj počítač.  
  
     Další informace najdete v dokumentaci služby IIS.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)