---
title: 'Chyba: Ladění neběží&#39;t možné, protože v systému je povolen ladicí program jádra | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.kernel_dbg_enabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- kernel debugger
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba943057da003a0fafee6d6fb8c6082d228779f9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="error-debugging-isn39t-possible-because-a-kernel-debugger-is-enabled-on-the-system"></a>Chyba: Ladění neběží&#39;t možné, protože v systému je povolen ladicí program jádra
Při ladění spravovaného kódu, zobrazí se následující chybová zpráva:  
  
```  
Debugging isn't possible because a kernel debugger is enabled on the system  
```  
  
 Tato zpráva se zobrazí při pokusu o ladění spravovaného kódu:  
  
-   na [!INCLUDE[win7](../debugger/includes/win7_md.md)] nebo [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)]systému, která byla spuštěna v režimu ladění.  
  
-   aplikace používá verze CLR CLR 2.0, 3.0 nebo 3.5.  
  
## <a name="solution"></a>Řešení  
  
#### <a name="to-fix-this-problem"></a>Chcete-li vyřešit tento problém  
  
-   Upgrade aplikace k používání CLR verze 4.0 nebo 4.5  
  
     —nebo—  
  
-   Zakázat ladění jádra a ladit v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     —nebo—  
  
-   Ladění pomocí ladicí program jádra místo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     —nebo—  
  
-   V ladicím programu jádra zakažte výjimky v uživatelském režimu.  
  
#### <a name="to-disable-kernel-debugging-in-the-current-session"></a>Chcete-li zakázat ladění jádra v aktuální relaci.  
  
-   V příkazovém řádku zadejte příkaz:  
  
    ```  
    Kdbgctrl.exe -d  
    ```  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-windows-vista-and-windows-7"></a>Chcete-li zakázat ladění jádra pro všechny relace (Windows Vista a Windows 7)  
  
1.  V příkazovém řádku zadejte příkaz:  
  
    ```  
    bcdedit /debug off   
    ```  
  
2.  Restartujte počítač.  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-other-windows-operating-systems"></a>Chcete-li zakázat ladění jádra pro všechny relace (jiné operační systémy Windows)  
  
1.  Vyhledejte soubor boot.ini na systémové jednotce (obvykle C:\\). Soubor boot.ini může být skryté a jen pro čtení. Tedy je nutné použít následující příkaz k jeho zobrazení:  
  
    ```  
    dir /ASH  
    ```  
  
2.  Otevřete soubor boot.ini pomocí poznámkového bloku a odeberte následující možnosti:  
  
    ```  
    /debug  
    /debugport  
    /baudrate  
    ```  
  
3.  Restartujte počítač.  
  
#### <a name="to-debug-with-the-kernel-debugger"></a>Chcete-li ladit pomocí ladicího programu jádra  
  
1.  Pokud je připojili ladicí program jádra, zobrazí se zpráva s dotazem, jestli chcete pokračovat k ladění. Klikněte na tlačítko Pokračovat.  
  
2.  Můžete získat `User break exception(Int 3).` Pokud k tomu dojde, zadejte následující příkaz ladicí program jádra pokračujte k ladění:  
  
     `gn`  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)