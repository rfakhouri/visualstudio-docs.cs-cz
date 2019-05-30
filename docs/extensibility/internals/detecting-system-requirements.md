---
title: Zjištění požadavků na systém | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- setup, VSPackages
- launch conditions
ms.assetid: 0ba94acf-bf0b-4bb3-8cca-aaac1b5d6737
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1ef76bc111fc48a717605f1beea74c4b91d0f2b4
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351633"
---
# <a name="detect-system-requirements"></a>Zjistit požadavky na systém
VSPackage nemůže fungovat, pokud je nainstalována aplikace Visual Studio. Když spravovat instalaci vašeho balíčku VSPackage pomocí Instalační služby systému Windows, můžete nakonfigurovat instalační program a zjistit, zda je nainstalována aplikace Visual Studio. Můžete také nakonfigurovat tak, zkontrolujte systém, hledá další požadavky, například konkrétní verzi Windows nebo určité množství paměti RAM.

## <a name="detect-visual-studio-editions"></a>Zjištění edice sady Visual Studio
 Pokud chcete zjistit, jestli je nainstalovaná edice sady Visual Studio, ověřte, že hodnota **nainstalovat** klíč registru je *(REG_DWORD) 1* v příslušné složce, jak je uvedeno v následující tabulce. Všimněte si, že hierarchii edice sady Visual Studio:

1. Enterprise

2. Professional

3. Komunita

Při instalaci na novější verzi klíče registru pro tuto verzi jsou přidány stejně jako u starších edicích. To znamená, pokud je nainstalovaná edice Enterprise, **nainstalovat** klíč nastavený na *1* pro organizace, a také pro edice Professional a Community. Proto je potřeba zkontrolovat pouze pro nejnovější verzi, které potřebujete.

> [!NOTE]
> V 64bitové verzi systému editor registru, 32bitová verze klíče se zobrazí v části **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\\** . Klíče aplikace Visual Studio jsou v rámci **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing\\** .

|Produkt|Key|
|-------------|---------|
|Visual Studio Enterprise 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\enterprise|
|Visual Studio Professional 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\professional|
|Visual Studio Community 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\community|
|Visual Studio 2015 Shell (integrovaný režim a izolovaný režim)|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell|

## <a name="detect-when-visual-studio-is-running"></a>Rozpoznat, kdy je spuštěná sada Visual Studio
 Vaše VSPackage nelze správně zaregistrovány, pokud je spuštěná sada Visual Studio při instalaci sady VSPackage. Instalační program musí rozpoznat, kdy je spuštěná sada Visual Studio a pak odmítnout instalaci programu. Instalační služby systému Windows neumožňuje použití položky tabulky k povolení takovéto zjišťování. Místo toho musíte vytvořit vlastní akci, následujícím způsobem: Použití `EnumProcesses` funkce pro detekci *devenv.exe* zpracovávat a potom buď nastavit vlastnost Instalační program, který se používá v podmínce spuštění nebo podmíněně zobrazit dialogové okno, které se zobrazí výzva k zavřete sadu Visual Studio.

## <a name="see-also"></a>Viz také:
- [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)