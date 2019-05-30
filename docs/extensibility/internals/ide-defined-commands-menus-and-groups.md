---
title: Příkazy definované prostředím IDE, nabídky a skupiny | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, environment-defined
- .vsct files, environment-defined constants
- command groups, environment-defined
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5158a9d1a06ec6f08c67777e4f1ce2e4d37220e3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315662"
---
# <a name="ide-defined-commands-menus-and-groups"></a>Příkazy, nabídky a skupiny definované integrovaným vývojovým prostředím
Počet nabídek, příkazy a skupinu příkazů jsou již definovány pro použití [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí. Tyto příkazy jsou také k dispozici pro použití při rozšíření [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="finding-environment-defined-commands"></a>Hledání příkazů prostředí definované
 Příkazy prostředí jsou definovány v sadě čtyři soubory .vsct:

- SharedCmdDef.vsct

- SharedCmdPlace.vsct

- ShellCmdDef.vsct

- ShellCmdPlace.vsct

  Tyto soubory jsou umístěny v  *\<Visual Studio SDK instalační_cesta >* \VisualStudioIntegration\Common\Inc\\. Tyto soubory poskytují definice a identifikátory GUID nabídek a skupiny, které můžete použít v souboru konfigurace (.vsct) tabulky příkazů z vašeho balíčku VSPackage jako kontejnery pro nabídky, skupiny a příkazy.

## <a name="in-this-section"></a>V tomto oddílu
- [Identifikátory GUID a ID nabídek sady Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)

 Poskytuje hodnoty GUID a ID nabídky na řádku nabídek sady Visual Studio a skupin, které obsahují.

- [Identifikátory GUID a ID panelů nástrojů sady Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)

 Poskytuje hodnoty GUID a ID panelů nástrojů v sadě Visual Studio IDE a skupin, které obsahují.

- [Identifikátory GUID a ID příkazů sady Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)

 Poskytuje hodnoty GUID a ID příkazy definované v integrovaném vývojovém prostředí sady Visual Studio.

## <a name="see-also"></a>Viz také
- [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [Příkazy definované prostředím IDE pro rozšíření systémů projektů](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)