---
title: Ladění aplikací ASP.NET nasazenou | Dokumentace Microsoftu
ms.date: 06/30/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASP.NET Web applications
- Web services, debugging
- XML, debugging Web services
- debugging Web services
- ASP.NET, debugging Web applications
- XML Web services, debugging
ms.assetid: b938a91b-be96-416f-83bc-4177e7f3929a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
ms.openlocfilehash: 57594775afe5d6708cd5d11b141f8cffc1b42e6c
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57525385"
---
# <a name="debugging-deployed-aspnet-applications"></a>Ladění aplikací nasazených ASP.NET
Použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladění nasazených aplikací, je nutné se připojit k [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovních procesů zpracování a ujistěte se, že ladicí program má přístup k symbolům pro aplikaci. Musíte také najít a otevřít zdrojové soubory pro aplikaci. Další informace najdete v tématu [zadejte symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md), [jak: Hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md), a [požadavky na systém](../debugger/aspnet-debugging-system-requirements.md).

> [!WARNING]
> Pokud se připojíte k [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovní proces pro ladění a stiskněte klávesu zarážku, všechen spravovaný kód v zastaví zpracování pracovního procesu. Zastavení veškerému spravovanému kódu v pracovním procesu, může způsobit zastavení práce pro všechny uživatele na serveru. Před ladění na provozním serveru vezměte v úvahu potenciální dopad na produkční práci.

Pro připojení k procesu [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] pracovního procesu je stejné jako připojení k jiné vzdálený proces. Pokud jste se připojili, pokud nemáte otevřený správný projekt, zobrazí se dialogové okno když se aplikace zastaví. Toto dialogové okno požádá o umístění zdrojových souborů pro aplikaci. Název souboru zadaný v symboly ladění na webovém serveru musí odpovídat názvu souboru, který zadáte v dialogovém okně. Další informace najdete v tématu [připojení k běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md). Chcete-li nastavit vzdálené ladění ve službě IIS, přečtěte si téma [vzdálené ladění ASP.NET ve vzdáleném počítači IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md).

> [!NOTE]
>  Mnoho [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webových aplikací odkazovat na knihovny DLL, které obsahují obchodní logikou nebo jiné užitečné kódu. Takový odkaz knihovny DLL zkopíruje ze svého místního počítače do složky \bin virtuální adresář webové aplikace při nasazení vaší aplikace. Při ladění, mějte na paměti, že vaše webová aplikace odkazuje na kopii knihovny DLL a nelze zkopírovat do místního počítače.

## <a name="see-also"></a>Viz také
- [Ladění aplikací ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)
- [Postupy: Povolení ladění pro aplikace ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)
- [Postupy: Hledání názvu procesu ASP.NET](../debugger/how-to-find-the-name-of-the-aspnet-process.md)
- [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)