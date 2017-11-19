---
title: "Příkazy definované IDE, nabídky a skupiny | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, environment-defined
- .vsct files, environment-defined constants
- command groups, environment-defined
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 032baaa57dd91cb07eac547da810d16e708f0828
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ide-defined-commands-menus-and-groups"></a>Příkazy definované IDE, nabídky a skupin
Mnoho nabídek, příkazy a příkaz skupiny jsou již definováni pro použití [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. Tyto příkazy jsou také k dispozici pro použití při rozšíření [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="finding-environment-defined-commands"></a>Hledání definované prostředí příkazy  
 Příkazy prostředí jsou definovány v sadě čtyři .vsct soubory:  
  
-   SharedCmdDef.vsct  
  
-   SharedCmdPlace.vsct  
  
-   ShellCmdDef.vsct  
  
-   ShellCmdPlace.vsct  
  
 Tyto soubory jsou umístěny v  *\<cesta instalace Visual Studio SDK >*\VisualStudioIntegration\Common\Inc\\. Tyto soubory poskytují definice a identifikátory GUID nabídky a skupiny, které můžete použít v souboru konfigurace (.vsct) tabulky příkaz vaší VSPackage jako kontejnery pro nabídky, skupin a příkazy.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Identifikátory GUID a ID nabídky sady Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)  
 Poskytuje hodnoty GUID a ID nabídky v řádku nabídek Visual Studio a skupin, které obsahují.  
  
 [Identifikátory panelů nástrojů Visual Studio a identifikátory GUID](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)  
 Poskytuje hodnoty GUID a ID panelů nástrojů v prostředí Visual Studio IDE a skupin, které obsahují.  
  
 [Identifikátory příkazů sady Visual Studio a identifikátory GUID](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)  
 Poskytuje hodnoty GUID a ID příkazy definované v prostředí Visual Studio IDE.  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Příkazy definované IDE pro rozšíření projektu systémy](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)   
 [Jak přidat VSPackages prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)