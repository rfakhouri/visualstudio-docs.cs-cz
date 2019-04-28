---
title: Zjištění požadavků na systém | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- setup, VSPackages
- launch conditions
ms.assetid: 0ba94acf-bf0b-4bb3-8cca-aaac1b5d6737
caps.latest.revision: 51
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 467554b8e50878bcdf1029e4792bbf168a09fa11
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445241"
---
# <a name="detecting-system-requirements"></a>Zjištění požadavků na systém
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

VSPackage nemůže fungovat, pokud je nainstalována aplikace Visual Studio. Když spravovat instalaci vašeho balíčku VSPackage pomocí Instalační služby systému Windows, můžete nakonfigurovat instalační program a zjistit, zda je nainstalována aplikace Visual Studio. Můžete také nakonfigurovat tak, zkontrolujte systém, hledá další požadavky, například konkrétní verzi Windows nebo určité množství paměti RAM.  
  
## <a name="detecting-visual-studio-editions"></a>Zjišťování edice sady Visual Studio  
 Pokud chcete zjistit, jestli je nainstalovaná edice sady Visual Studio, ověřte, že jako hodnotu klíče registru instalace (REG_DWORD) 1 v příslušné složce, jak je uvedeno v následující tabulce. Všimněte si, že hierarchii edice sady Visual Studio:  
  
1. Enterprise  
  
2. Professional  
  
3. Komunita  
  
   Pokud je nainstalovaná "vyšší" edici, se přidají klíče registru pro tuto verzi stejně jako u "nižší" edice. To znamená pokud je nainstalovaná edice Enterprise, nainstalujte klíč je nastavená na 1 pro organizace, a také pro edice Professional a Community. Proto je potřeba zkontrolovat jenom pro edici "nejvyšší", které potřebujete.  
  
> [!NOTE]
> V 64bitové verzi systému editor registru, 32bitová verze klíče se zobrazí v části HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\\. Klíče aplikace Visual Studio jsou v rámci HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing\\.  
  
|Produkt|Key|  
|-------------|---------|  
|Visual Studio Enterprise 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\enterprise|  
|Visual Studio Professional 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\professional|  
|Visual Studio Community 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\community|  
|Visual Studio 2015 Shell (integrovaný režim a izolovaný režim)|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell|  
  
## <a name="detecting-when-visual-studio-is-running"></a>Zjištění, kdy je spuštěná sada Visual Studio  
 Vaše VSPackage nelze správně zaregistrovány, pokud je spuštěná sada Visual Studio při instalaci sady VSPackage. Instalační program musí rozpoznat, kdy je spuštěná sada Visual Studio a pak odmítnout instalaci programu. Instalační služby systému Windows neumožňuje použití položky tabulky k povolení takovéto zjišťování. Místo toho musíte vytvořit vlastní akci, následujícím způsobem: Použití `EnumProcesses` funkce pro detekci proces devenv.exe a potom buď nastavit vlastnost Instalační program, který se používá v podmínce spuštění nebo podmíněně zobrazit dialogové okno, které se zobrazí výzva k zavřete sadu Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)
