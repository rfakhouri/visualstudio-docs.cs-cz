---
title: "Chyba: Kontrola zabezpečení selhala, protože správce služby IIS neodpověděla. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.iis_not_responding
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 85b96d9e1396933519da71e93bac075ee51af001
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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