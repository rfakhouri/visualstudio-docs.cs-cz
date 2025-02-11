---
title: Mezinárodní nastavení, prostředí, dialogové okno Možnosti
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 146aef659290df4302cc3bbb3d24a5bf6f1f01c8
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605646"
---
# <a name="options-dialog-box-environment--international-settings"></a>Dialogové okno Možnosti: Mezinárodní \> nastavení prostředí

V případě, že máte na počítači nainstalovanou více než jednu jazykovou verzi integrovaného vývojového prostředí (IDE), na stránce mezinárodní nastavení můžete změnit výchozí jazyk. K tomuto dialogovému oknu se dostanete tak, že v nabídce **nástroje** vyberete **Možnosti** a pak zvolíte **mezinárodní nastavení** ze složky **prostředí** .

**Jazyk**

Obsahuje seznam dostupných jazyků pro nainstalované jazykové verze produktu. Pokud se prostředí sdílí s více jazyky produktů nebo instalací smíšeného jazyka produktů, je výběr jazyka změněn na **stejný jako v systému Microsoft Windows**.

> [!CAUTION]
> V systému, v němž je nainstalováno více jazyků C++ , nejsou tímto nastavením ovlivněny nástroje pro Visual Build (CL. exe, Link. exe, NMAKE. exe, BSCMAKE. exe a související soubory). Tyto nástroje používají verzi pro poslední nainstalovaný jazyk. Nástroje sestavení pro dříve instalovaný jazyk jsou přepsány, protože nástroje pro C++ Visual Build nepoužívají model satelitní knihovny DLL.

### <a name="see-also"></a>Viz také:

- [Nainstalovat jazykové sady](../../install/install-visual-studio.md#step-6---install-language-packs-optional)