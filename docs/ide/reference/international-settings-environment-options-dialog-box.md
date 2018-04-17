---
title: Mezinárodní nastavení, prostředí, dialogové okno Možnosti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.InternationalSettings
- VS.ToolsOptionsPages.Environment.International_Settings
- VS.Environment.International Settings
- VS.ToolsOptionsPag.Environment.International_Settings
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
ms.openlocfilehash: 33e206e4c38b4bde715d72c6b8eb4b5bdf9c5dd8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="international-settings-environment-options-dialog-box"></a>Mezinárodní nastavení, prostředí, dialogové okno Možnosti
Stránka mezinárodní nastavení umožňuje změnit výchozí jazyk, když máte více než jedna jazyková verze integrované vývojové prostředí (IDE) v počítači nainstalován. Tohoto dialogového okna můžete přejít pomocí výběr **možnosti** z **nástroje** nabídky a pak vyberete **mezinárodní nastavení** z **prostředí** složky. Pokud tato stránka se nezobrazí v seznamu, vyberte **zobrazit všechna nastavení** v **možnosti** dialogové okno.  
  
> [!NOTE]
>  K dispozici v dialogových oken, názvy a umístění příkazy nabídky, které vidíte, se může lišit od co je popsáno v nápovědě v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
 **Jazyk**  
 Zobrazí seznam dostupných jazyků pro jazykové verze nainstalovaného produktu. Tato možnost není dostupná, pokud máte více než jedna jazyková verze v počítači nainstalován. Pokud více jazyky produktů nebo smíšený jazyk instalaci produktů sdílet prostředí, výběr jazyka se změní na **stejné jako Microsoft Windows**.  
  
> [!CAUTION]
>  V systému nainstalováno více jazyků nemá toto nastavení vliv nástroje sestavení Visual C++ (cl.exe, link.exe, nmake.exe, bscmake.exe a související soubory). Tyto nástroje používat verzi pro poslední jazyk nainstalovaný. Nástroje pro sestavení pro dříve nainstalované jazyk se přepíší, protože sestavení nástroje Visual C++ nepoužívejte model satelitní knihovny DLL.  
  
## <a name="see-also"></a>Viz také  
 [Nainstalujte jazykové sady](../../install/install-visual-studio.md#step-6---install-language-packs-optional)   
 [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)