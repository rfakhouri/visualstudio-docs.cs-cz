---
title: Instalace sady Visual Studio SDK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: c730edb6-5099-4c16-85a8-08def09f1455
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 259646e0dbee4831db83a7098954d1c5144d8ead
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
Protože se zatížení Visual Studio nebo součásti, můžete taky nainstalovat **vývoj rozšíření pro Visual Studio** zatížení (ID: Microsoft.VisualStudio.Workload.VisualStudioExtension) z příkazového řádku. V tématu [používání parametrů příkazového řádku pro instalaci sady Visual Studio](../install/use-command-line-parameters-to-install-visual-studio.md) podrobné informace o přepínačích příslušný příkazový řádek a obecné pokyny o určení zatížení nebo součást identifikátory.
  
 Všimněte si, že je nutné použít instalační program sady Visual Studio, který odpovídá nainstalovanou verzí sady Visual Studio. Například pokud máte Visual Studio Enterprise nainstalován v počítači, musíte spustit instalační program Visual Studio Enterprise (vs_enterprise.exe).