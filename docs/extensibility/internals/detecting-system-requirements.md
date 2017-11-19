---
title: "Zjišťování požadavky na systém | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup, VSPackages
- launch conditions
ms.assetid: 0ba94acf-bf0b-4bb3-8cca-aaac1b5d6737
caps.latest.revision: "50"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 92c4d51d575ffd6e5723bf80b8adc700b83f6afd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="detecting-system-requirements"></a>Zjišťování požadavky na systém
VSPackage nemůže fungovat, pokud je nainstalován nástroj Visual Studio. Pokud používáte ke správě instalaci vaší VSPackage Instalační služby systému Windows, můžete nakonfigurovat instalační program ke zjištění, jestli je nainstalovaná sada Visual Studio. Můžete také nakonfigurovat ho na zkontrolujte systém další požadavky, například, konkrétní verzi systému Windows nebo konkrétní velikosti paměti RAM.  
  
## <a name="detecting-visual-studio-editions"></a>Zjišťování edice sady Visual Studio  
 Pokud chcete zjistit, jestli je nainstalovaná edice sady Visual Studio, ověřte, zda hodnota klíče registru instalace (REG_DWORD) 1 ve složce odpovídající jak je uvedeno v následující tabulce. Všimněte si, zda je hierarchie edice sady Visual Studio:  
  
1.  Enterprise  
  
2.  Professional  
  
3.  Komunita  
  
 Když je nainstalovaný "vyšší" edition, se přidají klíče registru pro tuto edici také jako "nižší" edice. To znamená pokud je nainstalovaná verze Enterprise edition, nainstalujte klíč nastavena na hodnotu 1 pro organizace, a také pro edice Professional a Community. Proto je třeba zkontrolovat pouze pro "nejvyšší" edice, které potřebujete.  
  
> [!NOTE]
>  V 64bitové verzi editoru registru 32bitových klíčů se zobrazí v části HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\\. Visual Studio klíče jsou v části HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing\\.  
  
|Produkt|Key|  
|-------------|---------|  
|Visual Studio Enterprise 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\enterprise|  
|Visual Studio Professional 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\professional|  
|Visual Studio Community 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\community|  
|Prostředí Visual Studio 2015 (integrované a izolované)|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell|  
  
## <a name="detecting-when-visual-studio-is-running"></a>Zjištění, kdy běží v sadě Visual Studio  
 Vaše VSPackage nelze správně zaregistrovány, pokud Visual Studio je spuštěn, když je nainstalován VSPackage. Instalační program musí rozpoznat, kdy běží v sadě Visual Studio a pak odmítnout o instalaci programu. Instalační služba systému Windows není umožňují povolit takovéto zjišťování pomocí položky tabulky. Místo toho musíte vytvořit vlastní akci, následujícím způsobem: použití `EnumProcesses` funkce ke zjišťování procesu devenv.exe a pak nastavte ve vlastnosti Instalační program, který se používá v podmínce spuštění nebo podmíněně zobrazit dialogové okno s dotazem, zavřete Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Instalace VSPackages pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)