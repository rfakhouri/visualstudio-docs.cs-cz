---
title: Rozšíření a přizpůsobení nástroje systému Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- user interfaces, essentials
- tool windows, standard
ms.assetid: 46b2892e-7b2b-4b3f-83a7-b884f1e114ee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2ef4f656ed7b7ab7facbcfb470fca98327276cce
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="extending-and-customizing-tool-windows"></a>Rozšíření a přizpůsobení okna nástrojů
Visual Studio poskytuje několik různých typů systému windows, například nástroj windows, windows dokumentu a dialogové okno windows. Další windows například vlastnosti okna, ve výstupním okně a okno seznam úloh jsou typy nástroje systému windows.  
  
## <a name="tool-windows"></a>Nástroje systému Windows  
 Okna nástrojů Visual Studio jsou obvykle jen pro čtení systému windows, které nejsou založené na souborech. V tomto se liší od okna dokumentu, které budou zobrazovat soubory v režimu pro čtení a zápis. **Sada nástrojů**, **Průzkumníku řešení**, **vlastnosti** okně a **webový prohlížeč** jsou příklady nástroje systému windows.  
  
 Postup vytvoření jednoduchého nástroje okna naleznete v tématu [přidání okno nástroje](../extensibility/adding-a-tool-window.md).  
  
 Okno nástroje zaregistrovat pomocí sady Visual Studio, najdete v tématu [registrace okno nástroje](../extensibility/registering-a-tool-window.md).  
  
 Nástroje systému windows jsou jednou instancí ve výchozím nastavení, což znamená, že pouze jedna instance panel nástrojů je možné otevřít v čase. Po otevření okna Nástroj jedné instance zůstane otevřené, dokud je uzavřený rozhraní IDE. Pokud zavřete okno jednou instancí nástroje, změní jenom jeho viditelnost. Můžete také vytvořit více instancemi nástroj windows tak, aby více instancí okna je možné otevřít současně. V tématu [vytváření okno nástroj s více instancemi](../extensibility/creating-a-multi-instance-tool-window.md) Další informace.  
  
 Nástroje systému windows může být *dynamické*, což znamená, že jsou viditelné vždy, když platí jejich související kontextu uživatelského rozhraní. Použití automatického viditelnost může snížit zbytečné soubory systému windows v prostředí IDE. Další informace najdete v tématu [otevírání dynamické okno nástroje](../extensibility/opening-a-dynamic-tool-window.md).  
  
 Nástroje systému windows může být ukotveného, plovoucí nebo v rámci dokumentů s kartami. Rámce okna nástrojů poskytuje prostředí IDE a slouží k řízení velikosti, umístění, ukotvení stavu a další vlastnosti, trvalé. V podokně okna Nástroj zobrazí obsah. Výchozí velikost a umístění použít, pouze když je nástroj prvním otevření okna; po který je uložen stav okno nástroje.  
  
 Podokna nástroje můžete hostovat uživatelských ovládacích prvků grafického subsystému WPF a podporoval panely nástrojů. Je možné přepsat <xref:Microsoft.VisualStudio.Shell.WindowPane.Window%2A> vlastnost vrátit popisovač hostované ovládacího prvku.  
  
 Nástroje systému Windows můžete přidat spoustu různých funkcí. Například můžete přidat na panel nástrojů: [přidání panelu nástrojů na okno nástroje](../extensibility/adding-a-toolbar-to-a-tool-window.md) nebo z místní nabídky: [Přidání místní nabídky v okně nástroje](../extensibility/adding-a-shortcut-menu-in-a-tool-window.md). Můžete přidat ovládací prvek vyhledávání, která umožňuje vyhledat položky v rámci vaší okno nástroje: [přidání vyhledávání okno nástroje](../extensibility/adding-search-to-a-tool-window.md).  
  
 Přihlásíte k odběru události okno nástroj: [odběr pro událost](../extensibility/subscribing-to-an-event.md).  
  
## <a name="extending-existing-tool-windows"></a>Rozšíření stávající nástroj Windows  
 Budete moct přidat informace o vaší okno nástroje na nový **možnosti** stránky a nové nastavení na **vlastnosti** stránky, zapisovat **seznam úkolů** a **výstup**  systému windows. Další informace najdete v tématu [rozšíření vlastností, seznam úkolů, výstupní a možnosti Windows](../extensibility/extending-the-properties-task-list-output-and-options-windows.md) a [rozšíření vlastností, seznam úkolů, výstupní a možnosti Windows](../extensibility/extending-the-properties-task-list-output-and-options-windows.md).  
  
## <a name="modal-dialog-boxes"></a>Modální dialogová okna  
 V rozšíření sady Visual Studio by měl vytvořit modální dialogová okna odvozením z <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>, která umožňuje řídit je a zbytek z uživatelského rozhraní. Další informace najdete v tématu. [Vytváření a správa modální dialogová okna](../extensibility/creating-and-managing-modal-dialog-boxes.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření rozšíření pomocí panelu nástrojů](../extensibility/creating-an-extension-with-a-tool-window.md)