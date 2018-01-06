---
title: Instalace sady Visual Studio SDK | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: visual-studio-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c730edb6-5099-4c16-85a8-08def09f1455
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 13ce2a839c09aa65c2bed2d87aec63827ec6583c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="installing-the-visual-studio-sdk"></a>Instalace sady Visual Studio SDK
Visual Studio SDK je volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později.  
  
## <a name="installing-the-visual-studio-sdk-as-part-of-a-visual-studio-installation"></a>Instalace sady Visual Studio SDK jako součást instalace sady Visual Studio  
 Pokud chcete zahrnout VSSDK instalace Visual Studia, nainstalujte **vývoj rozšíření pro Visual Studio** zatížení v rámci **ostatní modulové**. Dojde k instalaci sady Visual Studio SDK, jakož i nezbytných předpokladů. Instalaci můžete vyladit další výběrem nebo zobrazení unselecting součásti ze souhrnu. 
  
## <a name="installing-the-visual-studio-sdk-after-installing-visual-studio"></a>Instalace sady Visual Studio SDK po instalaci sady Visual Studio  
 Pokud se rozhodnete nainstalovat sadu Visual Studio SDK po dokončení instalace Visual Studia, znovu spusťte instalační program sady Visual Studio a vyberte **vývoj rozšíření pro Visual Studio** zatížení.  
  
## <a name="installing-the-visual-studio-sdk-from-a-solution"></a>Instalace sady Visual Studio SDK z řešení  
 Pokud otevřete řešení s projektem rozšiřitelnost bez první instalaci VSSDK, zobrazí se výzva podle zvýrazněná informační panel výše Průzkumníku řešení. By měl vypadat přibližně takto:  
  
 ![SolutionExplorerInstall](../extensibility/media/solutionexplorerinstall.png "SolutionExplorerInstall")  
  
## <a name="installing-the-visual-studio-sdk-from-the-command-line"></a>Instalace sady Visual Studio SDK z příkazového řádku  
Stejně jako u zatížení Visual Studio nebo součásti, můžete také nainstalovat položku z příkazového řádku. V tématu [používání parametrů příkazového řádku pro instalaci sady Visual Studio](../install/use-command-line-parameters-to-install-visual-studio.md) podrobnosti o přepínače příslušný příkazový řádek a jak určit identifikátory zatížení nebo součást.
  
 Všimněte si, že je nutné použít instalační program sady Visual Studio, který odpovídá nainstalovanou verzí sady Visual Studio. Například pokud máte Visual Studio Enterprise nainstalován v počítači, musíte spustit instalační program Visual Studio Enterprise (vs_enterprise.exe).