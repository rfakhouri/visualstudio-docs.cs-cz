---
title: Mezinárodní nastavení, prostředí, dialogové okno Možnosti
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.InternationalSettings
- VS.ToolsOptionsPages.Environment.International_Settings
- VS.Environment.International Settings
helpviewer_keywords:
- International Settings dialog box
- languages, environment settings
- Options dialog box, international settings
- languages, specifying default
ms.assetid: e3a8815c-6995-4099-8e88-34f91fad55b2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1609f33230942c2f5d026eb072e3e85860137d4b
ms.sourcegitcommit: 1abb9cf4c3ccb90e3481ea8079272c98aad12875
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2018
ms.locfileid: "50143148"
---
# <a name="international-settings-environment-options-dialog-box"></a>Mezinárodní nastavení, prostředí, dialogové okno Možnosti

Stránka mezinárodní nastavení umožňuje změnit výchozí jazyk v případě, že máte více než jedna jazyková verze sady integrovaného vývojového prostředí (IDE) na vašem počítači nainstalovaný. Můžete přístup k tomuto dialogovému oknu výběrem **možnosti** z **nástroje** nabídky a následným výběrem možnosti **mezinárodní nastavení** z **prostředí** složky. Pokud se tato stránka se nezobrazí v seznamu, vyberte **zobrazit všechna nastavení** v **možnosti** dialogové okno.

> [!NOTE]
> Dostupné možnosti v dialogových oknech, názvy a umístění příkazů, které vidíte, mohou lišit od informací uvedených v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).

 **Jazyk** uvádí dostupné jazyky pro jazykové verze nainstalovaného produktu. Tato možnost není dostupná, pokud máte více než jedna jazyková verze na vašem počítači nainstalovaný. Pokud více jazyků produktů nebo smíšený jazyk instalace produktů sdílet prostředí, se změní výběr jazyka na **totéž jako Windows Microsoft**.

> [!CAUTION]
> V systému s více jazyky, které jsou nainstalované nástroje sestavení jazyka Visual C++ (cl.exe, link.exe, nmake.exe, bscmake.exe a související soubory) nejsou ovlivněny toto nastavení. Tyto nástroje používat verzi pro poslední jazyk nainstalovaný. Nástroje sestavení pro dříve nainstalované jazyky jsou přepsány, protože nástroje sestavení jazyka Visual C++ se nepoužívá model satelitní knihovny DLL.

## <a name="see-also"></a>Viz také

- [Instalace jazykové sady](../../install/install-visual-studio.md#step-6---install-language-packs-optional)
- [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)