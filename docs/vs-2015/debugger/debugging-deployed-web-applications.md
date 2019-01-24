---
title: Ladění nasazených webových aplikací | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ASP.NET Web applications
- Web services, debugging
- XML, debugging Web services
- debugging Web services
- ASP.NET, debugging Web applications
- XML Web services, debugging
ms.assetid: b938a91b-be96-416f-83bc-4177e7f3929a
caps.latest.revision: 34
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d7b7a95af1922f5ad57d15fb53dcba561a9f139e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54800998"
---
# <a name="debugging-deployed-web-applications"></a>Ladění nasazených webových aplikací
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Budete potřebovat pro ladění webové aplikace, na kterém běží na provozním serveru, má počítat opatrně. Pokud se připojíte k [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovní proces pro ladění a použijte zarážku, například všechny spravovaného kódu v procesu zastaví pracovního procesu. Zastavení veškerému spravovanému kódu v pracovním procesu, může způsobit zastavení práce pro všechny uživatele na serveru. Před ladění na provozním serveru vezměte v úvahu potenciální dopad na produkční práci.  
  
 Použití [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ladění nasazených aplikací, je nutné se připojit k [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovních procesů zpracování a ujistěte se, že ladicí program má přístup k symbolům pro aplikaci. Musíte také najít a otevřít zdrojové soubory pro aplikaci. Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md), [jak: Hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md), a [požadavky na systém](../debugger/aspnet-debugging-system-requirements.md).  
  
> [!NOTE]
>  Mnoho [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] webových aplikací odkazovat na knihovny DLL, které obsahují obchodní logikou nebo jiné užitečné kódu. Takový odkaz automaticky zkopíruje knihovny DLL ze svého místního počítače do složky \bin virtuální adresář webové aplikace. Při ladění, mějte na paměti, že vaše webová aplikace odkazuje na kopii knihovny DLL a nelze zkopírovat do místního počítače.  
  
 Pro připojení k procesu [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] pracovního procesu je stejné jako připojení k jiné vzdálený proces. Pokud jste se připojili, pokud nemáte otevřený správný projekt, zobrazí se dialogové okno když se aplikace zastaví. Toto dialogové okno požádá o umístění zdrojových souborů pro aplikaci. Název souboru zadaný v symboly ladění na webovém serveru musí odpovídat názvu souboru, který zadáte v dialogovém okně. Další informace najdete v tématu [připojení k běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací ASP.NET a AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Ladění webových aplikací a skriptu](../debugger/debugging-web-applications-and-script.md)   
 [Postupy: Povolit ladění pro aplikace ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)   
 [Postupy: Hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
