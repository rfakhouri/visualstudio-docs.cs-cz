---
title: "Postupy: spuštění pracovního procesu pod uživatelským účtem | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- user accounts, aspnet_wp.exe
- ASP.NET, debugging Web applications
- tools, aspnet_wp.exe
- ASP.NET, tools
- aspnet_wp.exe
ms.assetid: b58e97b1-e62a-4318-aea4-52276ea20735
caps.latest.revision: "32"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b823675623f20df49edb87582f3e40695aec50e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-run-the-worker-process-under-a-user-account"></a>Postupy: Spuštění pracovního procesu v rámci uživatelského účtu
Chcete-li nastavit v počítači, takže můžete spustit [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces (aspnet_wp.exe nebo w3wp.exe) pod uživatelským účtem, postupujte podle těchto kroků.  

 > [!IMPORTANT]
 > Od verze Windows Server 2008 R2, doporučujeme použít [ApplicationPoolIdentity](https://docs.microsoft.com/en-us/iis/manage/configuring-security/application-pool-identities) jako identity pro každý fond aplikací.
  
## <a name="procedure"></a>Postup  
  
#### <a name="to-run-aspnetwpexe-under-a-user-account"></a>Ke spuštění aspnet_wp.exe pod uživatelským účtem  
  
1.  Otevřete soubor machine.config, umístěný ve vašem počítači ve složce Konfigurace na cestě, kam jste nainstalovali modulu runtime.  
  
2.  Najít &lt;processModel&gt; části a změňte atributy uživatele a heslo pro jméno a heslo uživatelského účtu, který chcete aspnet_wp.exe běh.  
  
3.  Uložení souboru machine.config.  
  
4.  Na [!INCLUDE[winxpsvr](../debugger/includes/winxpsvr_md.md)], ve výchozím nastavení je nainstalována služba IIS 6.0. Odpovídající pracovní proces je w3wp.exe.To v režimu aspnet_wp.exe jako pracovní proces služby IIS 6.0, postupujte takto:  
  
    1.  Klikněte na tlačítko **spustit**, klikněte na tlačítko **nástroje pro správu** a potom zvolte **Internetová informační služba**.  
  
    2.  V **Internetová informační služba** dialogové okno, klikněte pravým tlačítkem myši **weby** složky a vyberte **vlastnosti**.  
  
    3.  V **webové servery – vlastnosti** dialogovém okně vyberte **služby**.  
  
    4.  Vyberte **spustit webovou službu v izolovaném režimu IIS6.0**.  
  
    5.  Zavřít **vlastnosti** dialogové okno a **Správce služeb Internetu**.  
  
5.  Otevřete příkazový řádek systému Windows a obnovte server spuštěním:  
  
    ```  
    iisreset  
    ```  
    – nebo –  
  
    ```  
    net stop iisadmin /y  
    net start w3svc  
    ```  
  
6.  Vyhledejte dočasný [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] složce se soubory, které by měly mít stejnou cestu jako složce Konfigurace. Klikněte pravým tlačítkem na dočasnou [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] soubory složky a vyberte **vlastnosti** v místní nabídce.  
  
7.  V **dočasné soubory vlastnosti ASP.NET** dialogové okno, klikněte na tlačítko **zabezpečení** kartě.  
  
8.  Klikněte na tlačítko **rozšířené**.  
  
9. V **Upřesnit nastavení zabezpečení pro Temporary ASP.Net Files** dialogové okno, klikněte na tlačítko **přidat**.  
  
    **Dialogové okno Vybrat uživatele, počítače nebo skupiny** se zobrazí.  
  
10. Zadejte uživatelské jméno v **zadejte název objektu k výběru** pole a pak klikněte na **OK**. Uživatelské jméno musí mít tento formát: Název_domény\uživatelské_jméno.  
  
11. V **položka oprávnění pro Temporary ASP.NET Files** dialogové okno pole, uživateli přidělit **úplné řízení**a potom klikněte na **OK** zavřete **položka pro dočasné ASP Soubory .NET** dialogové okno.  
  
12. A **zabezpečení** se zobrazí dialogové okno a požádá, pokud Opravdu chcete změnit oprávnění pro složku systému. Klikněte na tlačítko **Ano**.  
  
13. Klikněte na tlačítko **OK** zavřete **dočasné soubory vlastnosti ASP.NET** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
[Ladění aplikací ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)   
[ASP.NET ladění: Systémové požadavky](../debugger/aspnet-debugging-system-requirements.md)  
  
