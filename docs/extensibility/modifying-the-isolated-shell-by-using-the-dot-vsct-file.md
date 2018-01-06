---
redirect_url: shell/modifying-the-isolated-shell-by-using-the-dot-vsct-file
title: "Úprava izolované prostředí pomocí. Soubor Vsct | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .vsct file
ms.assetid: 6d147c2d-10e9-400e-b8ce-5566287b41ba
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ddf48e384b85946d4efcbb62359f24780507dfa4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="modifying-the-isolated-shell-by-using-the-vsct-file"></a>Úprava izolované prostředí pomocí. Soubor Vsct
Projekt uživatelského rozhraní pro projekt sady Visual Studio izolované prostředí obsahuje .vsct soubor, který umožňuje určit, které skupiny aplikací a jednotlivé příkazy jsou k dispozici v aplikaci. Toto je výňatek ze souboru .vsct beze změny.  
  
```  
<!-- <Define name="No_WindowListCommand"/> -->  
<!-- <Define name="No_MoreWindowsCommand"/> -->  
<!-- <Define name="No_PaneNextPaneCommand"/> -->  
<!-- <Define name="No_PanePrevPaneCommand"/> -->  
```  
  
 Ve výchozím nastavení většina příkazů a příkaz skupiny jsou zahrnuty. Vyloučit příkaz nebo skupina příkazu, jednoduše zrušte komentář u dané příkaz nebo skupiny.  
  
 Například pokud chcete odebrat další podokno a předchozích příkazů podokně, zrušte komentář u `No_PaneNextPaneCommand` a `No_PanePrevPaneCommand` položky:  
  
```  
  
<Define name="No_PaneNextPaneCommand"/> <Define name="No_PanePrevPaneCommand"/>  
  
```  
  
 Podrobnější příklad toto vlastní nastavení, najdete v části [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
## <a name="referenced-files"></a>Odkazované soubory  
 Výchozí soubor .vsct pro aplikaci odkazuje na následující soubory. Tyto soubory jsou umístěny v podadresáři \VisualStudioIntegration\Common\Inc\ instalační adresář nástroje Visual Studio SDK.  
  
|Soubor|Popis|  
|----------|-----------------|  
|wbids.h|Identity uživatelského rozhraní pro webové procházení balíček.|  
|AppIDCmdUsed.vsct|Příkaz Tabulka pro základní prvky uživatelského rozhraní Visual Studio.|  
|EmulatorCmdUsed.vsct|Příkaz Tabulka pro Emacs a Brief prvky uživatelského rozhraní editoru emulace.|  
|Vsdebugguids.h|Definuje identifikátory GUID příkazy, stránka Možnosti a další funkce ladicího programu sady Visual Studio.|  
|VsDbgCmdUsed.vsct|Příkaz Tabulka pro ladicí program.|  
  
 Soubor AppIDCmdUsed.vsct obsahuje prvky uživatelského rozhraní Visual Studio podle symboly definované v souboru .vsct aplikace.  
  
 Další informace najdete v tématu [návrh tabulky příkaz XML (. Soubory Vsct)](../extensibility/internals/designing-xml-command-table-dot-vsct-files.md) a [referenční dokumentace schématu VSCT XML](../extensibility/vsct-xml-schema-reference.md).  
  
## <a name="see-also"></a>Viz také  
 [Izolované prostředí sady Visual Studio](../extensibility/visual-studio-isolated-shell.md)