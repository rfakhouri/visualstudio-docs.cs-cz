---
title: Zobrazení souborů pomocí příkazu Otevřít soubor | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project types, supporting Open File command
- Open File command
- persistence, supporting Open File command
ms.assetid: 4fff0576-b2f3-4f17-9769-930f926f273c
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 139eb83f2260c44a3e0f8c50868d42aca8160694
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673426"
---
# <a name="displaying-files-by-using-the-open-file-command"></a>Zobrazení souborů pomocí příkazu Otevřít soubor
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [zobrazení souborů pomocí příkazu Otevřít soubor](https://docs.microsoft.com/visualstudio/extensibility/internals/displaying-files-by-using-the-open-file-command).  
  
Následující kroky popisují, jak zachází s integrovaného vývojového prostředí **otevřít soubor** příkaz, který je k dispozici na **souboru** v nabídce [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Kroky také popisují, jak by měl projekty reakce na volání, které pocházejí z tohoto příkazu.  
  
 Když uživatel klikne **otevřít soubor** příkaz **souboru** nabídky a vybere soubor z **otevřít soubor** dialogové okno, se spustí následující proces.  
  
1.  Pomocí spuštěnou tabulku dokumentů, rozhraní IDE zjistí, zda soubor je již otevřen v projektu.  
  
    -   Pokud je soubor otevřen, rozhraní IDE resurfaces okna.  
  
    -   Pokud soubor není otevřen, zavolá rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> k dotazování každý projekt k určení, které projekty můžou otevřít soubor.  
  
        > [!NOTE]
        >  Ve vaší implementaci projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>, zadejte hodnotu priority, která určuje úroveň, na které váš projekt otevře soubor. Hodnoty priority jsou součástí <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> výčtu.  
  
2.  Každý projekt jako odpověď vrátí úroveň priority, která určuje význam umístí na se projekt k otevření souboru.  
  
3.  Integrované vývojové prostředí používá k určení, který projekt otevře soubor následující kritéria:  
  
    -   Projekt, který odpovídá nejvyšší prioritu (DP_Intrinsic) otevře soubor. Pokud více než jeden projekt odpoví tuto prioritu, první projekt reagovat otevře soubor.  
  
    -   Pokud žádný projekt odpoví s nejvyšší prioritou (DP_Intrinsic), ale všechny projekty odpověď s stejné, nižší prioritu, aktivní projekt otevře soubor. Pokud není aktivní žádný projekt, první projekt reagovat otevře soubor.  
  
    -   Pokud žádný projekt deklarací vlastnictví souboru (DP_Unsupported), ostatních souborech projektu se otevře soubor.  
  
         Pokud je vytvořena instance ostatních souborech projektu, projektu s hodnotou DP_CanAddAsExternal vždy odpovídá. Tato hodnota označuje, že projekt můžete otevřít soubor. Tento projekt se používá k umístění otevřených souborů, které nejsou v každém projektu. Seznam položek v tomto projektu není trvalý; Tento projekt je viditelný v **Průzkumníka řešení** pouze pokud je použit k otevření souboru.  
  
         Pokud projekt ostatní soubory neznamená, že ho můžete otevřít soubor, instance projektu nebyl vytvořen. V tomto případě rozhraní IDE vytvoří instanci projektu různých souborů a dává pokyn k otevření souboru projektu.  
  
4.  Jakmile rozhraní IDE zjistí, který projekt otevře soubor, volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> metoda u tohoto projektu.  
  
5.  Projekt nemá možnost otevření souboru pomocí editoru specifické pro projekt nebo standardní editor. Další informace najdete v tématu [jak: otevřít editoru pro konkrétní projekt](../../extensibility/how-to-open-project-specific-editors.md) a [jak: otevřít standardní editory](../../extensibility/how-to-open-standard-editors.md)v uvedeném pořadí.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení souborů pomocí příkazu Otevřít](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)   
 [Otevření a uložení položek projektu](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Postupy: otevření editoru pro konkrétní projekt](../../extensibility/how-to-open-project-specific-editors.md)   
 [Postupy: Otevření standardních editorů](../../extensibility/how-to-open-standard-editors.md)

