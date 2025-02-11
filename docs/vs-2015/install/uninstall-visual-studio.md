---
title: Odinstalace sady Visual Studio 2015 | Dokumentace Microsoftu
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
f1_keywords:
- uninstalling
- uninstalling visual studio
- uninstall
- uninstall Visual Studio
ms.assetid: 0e445255-b796-426d-ad93-a4d8e36da2c5
caps.latest.revision: 9
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: ed9d33501644c6fa7252dffa758f92c0919653b1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546899"
---
# <a name="uninstall-visual-studio"></a>Odinstalace sady Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio, naleznete v tématu [odinstalujte Visual Studio](/visualstudio/install/uninstall-visual-studio).

Tato stránka vás provede odinstalací sady Visual Studio 2015, starší verzi naší integrované sady nástrojů podporujících produktivitu pro vývojáře.

## <a name="uninstall-visual-studio-by-using-the-standard-uninstallation-method"></a>Odinstalace sady Visual Studio pomocí metody "standard" odinstalace

1. V **ovládací panely**na **programy a funkce** zvolte edici produktu, kterou chcete odinstalovat a pak zvolte **změnu**.

2. V Průvodci instalací zvolte **odinstalovat**, zvolte **Ano**a pak postupujte podle pokynů v průvodci.

   Tento standard nebo výchozí, způsob zachová některé položky, které se při první instalaci sady Visual Studio původně nainstalovaná (třeba Microsoft .NET Framework, Microsoft distribuovatelné součásti Visual C++, Microsoft SQL Server atd.).   Tyto položky zůstávají nainstalované, protože na nich závisí řada dalších aplikací. Ale pokud byste chtěli moc je odebrat, vyberte jejich položky na **programy a funkce**a pak je postupně odeberte.

## <a name="uninstall-visual-studio-and-all-other-related-files-that-is-to-uninstall-almost-everything"></a>Odinstalace sady Visual Studio a všech dalších souvisejících souborů (to znamená, že odinstalace téměř všeho)

1. Vyhledejte soubor .exe sady Visual Studio (vyhledejte například "vs_enterprise.exe").

    > [!NOTE]
    > Soubor by měl být v podsložce "%ProgramData%\Package Cache", například: C:\ProgramData\Package Cache\\{37e19555-e88d-4aed-9d42-82d0784d2b79}\vs_enterprise.exe

2. Spusťte soubor .exe s použitím / uninstall/force parametry příkazového řádku.

     Například spusťte ```vs_enterprise.exe /uninstall /force```, které se při výchozí odinstalaci odebrat sady Visual Studio a většina hlavních komponent, které se zachovají. Ale neodebere veškerý další obsah tohoto doplňky sady Visual Studio a rozšíření můžete nainstalovat (pro příklad, aktualizace sady Visual Studio a další volitelné komponenty).

    > [!TIP]
    > Alternativně můžete použít "**Total Uninstaller**" nástroj odebrat všechno, co sady Visual Studio nebo mít nainstalovány aktualizace sady Visual Studio. To znamená všechny verze sady Visual Studio 2013 nebo novější. Další informace najdete v článku [nástroje Visual Studio Uninstaller](https://github.com/Microsoft/VisualStudioUninstaller/releases) na Githubu.

## <a name="uninstall-visual-studio-in-silent-or-passive-modes-that-is-to-uninstall-from-source"></a>Odinstalace sady Visual Studio v tichém nebo pasivním režimu (tedy odinstalace ze zdroje)

1. V počítači s nainstalovanou sadou Visual Studio otevřete okno příkazového řádku systému Windows.

2. Zadejte následující parametry:

     *DVDRoot* \\< Instalační_soubor\> \</quiet&#124;/passive > [/ norestart] / uninstall

## <a name="roll-back-to-a-previous-version-or-release-of--visual-studio"></a>Vrátit se zpět k předchozí verzi nebo verzi aplikace Visual Studio

1. Odinstalace sady Visual Studio pomocí některé z metod uvedených v tomto tématu.

   > [!WARNING]
   > Odinstalace aktuální vydané verze sady Visual Studio (nebo aktualizace sady Visual Studio) a potom instalaci předchozí verze nemusí fungovat podle očekávání.
   >
   > Výsledek závisí na tom, kterou verzi nebo verzi sady Visual Studio nainstalujete, které verze komponent jsou nainstalované, které nainstalované produkty můžou mít závislosti buď verzi nástroje Visual Studio nebo její součásti a nakonec na jaké dřívější verze sady Visual Studio, které chcete nainstalovat nebo přeinstalovat.  Kvůli všem těmto proměnným standardní odinstalace bude často zachová komponenty, které nemusí fungovat s předchozími verzemi sady Visual Studio nebo verzí.
   >
   > Proto pro dosažení nejlepších výsledků doporučujeme použít [nástroje Visual Studio Uninstaller](https://github.com/Microsoft/VisualStudioUninstaller/releases).

2. Nainstalujte nebo přeinstalujte předchozí verzi sady Visual Studio, kterou chcete použít.

   I v případě, že můžete nainstalovat předchozí verzi sady Visual Studio, instalační program může přesto pokusit použít novější verzi nebo pokud je k dispozici. Podrobnější informace najdete v článku [jak: Instalace konkrétní verze sady Visual Studio](../install/how-to-install-a-specific-release-of-visual-studio.md) tématu.

## <a name="see-also"></a>Viz také:

- [Instalace sady Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)