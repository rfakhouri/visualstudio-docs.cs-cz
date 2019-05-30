---
title: Rozšíření a přizpůsobení nástrojů Windows | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- user interfaces, essentials
- tool windows, standard
ms.assetid: 46b2892e-7b2b-4b3f-83a7-b884f1e114ee
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c0eafb5a95151d6c3a805ad4d51c847f2fbe269d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341147"
---
# <a name="extend-and-customize-tool-windows"></a>Rozšířit a přizpůsobit panely nástrojů
Visual Studio poskytuje několik různých typů systému windows, například okna nástrojů, okna dokumentu a dialogové okno windows. Ostatní okna, jako **vlastnosti** okně **výstup** okno a **seznamu úkolů** okna, jsou druhy oken nástrojů.

## <a name="tool-windows"></a>Nástroje systému windows
 Okna nástrojů Visual Studio jsou obvykle jen pro čtení systému windows, které nejsou založené na souborech. To se liší od okna dokumentu, které zobrazí soubory v režimu čtení i zápis. **Nástrojů**, **Průzkumníka řešení**, **vlastnosti** okně a **webový prohlížeč** jsou příklady oken nástrojů.

 Zjistěte, jak vytvořit okno jednoduchý nástroj, najdete v článku [přidat panel nástrojů](../extensibility/adding-a-tool-window.md).

 Registrace panelu nástrojů pomocí sady Visual Studio, naleznete v tématu [registrace panelu nástrojů](../extensibility/registering-a-tool-window.md).

 Okna nástrojů jsou jednou instancí ve výchozím nastavení, což znamená, že pouze jedna instance panelu nástrojů je možné otevřít v čase. Po otevření okna nástroje jednou instancí, zůstane otevřený, dokud není zavřena integrovaného vývojového prostředí. Při zavření okna nástroje jednou instancí se změní pouze jejich viditelnost. Můžete také vytvořit více instancí okna nástrojů tak, aby více instancí okno může být otevřeno současně. Zobrazit [vytvořit panel nástrojů s více instancemi](../extensibility/creating-a-multi-instance-tool-window.md) Další informace.

 Nástroje systému windows může být *dynamické*, což znamená, že jsou viditelné pokaždé, když se použije jejich související kontextu uživatelského rozhraní. Použití automatického viditelnost můžete přehlednost oken v integrovaném vývojovém prostředí. Další informace najdete v tématu [otevření dynamického panelu nástrojů](../extensibility/opening-a-dynamic-tool-window.md).

 Nástroje systému windows může být ukotvených, s plovoucí desetinnou čárkou nebo v rámci dokument s kartami. Rámec okna nástrojů poskytuje rozhraní IDE a slouží k řízení velikosti, umístění, dokovací stavu a další trvalé vlastnosti. V podokně okna nástroje se zobrazí obsah. Výchozí velikost a umístění použít, pouze pokud panel nástrojů nejprve otevřen; potom se ukládají stav okna nástrojů.

 Nástroj podokna můžete hostovat uživatelské ovládací prvky WPF a podporovat panely nástrojů. Je možné přepsat <xref:Microsoft.VisualStudio.Shell.WindowPane.Window%2A> vlastnost vrátí popisovač hostovaného ovládacího prvku.

 Do okna nástrojů můžete přidat řadu různých funkcí. Můžete například přidat panel nástrojů: [Přidání panelu nástrojů do panelu nástrojů](../extensibility/adding-a-toolbar-to-a-tool-window.md) nebo z místní nabídky: [Přidat místní nabídku v panelu nástrojů](../extensibility/adding-a-shortcut-menu-in-a-tool-window.md). Můžete přidat ovládací prvek pro hledání, který umožňuje vyhledávat položky uvnitř okna nástroje: [Přidání vyhledávání do panelu nástrojů](../extensibility/adding-search-to-a-tool-window.md).

 Vám může přihlásit k odběru událostí okna nástroje: [Přihlásit odběr události](../extensibility/subscribing-to-an-event.md).

## <a name="extend-existing-tool-windows"></a>Rozšířit stávající nástroje systému windows
 Můžete přidat informace o okno nástroje na novou **možnosti** stránky a nové nastavení na **vlastnosti** stránky, zapisovat **seznamu úkolů** a **výstup**  systému windows. Další informace najdete v tématu [rozšířit vlastnosti, seznam úkolů, výstupu a možnosti windows](../extensibility/extending-the-properties-task-list-output-and-options-windows.md) a [rozšířit vlastnosti, seznam úkolů, výstupu a možnosti windows](../extensibility/extending-the-properties-task-list-output-and-options-windows.md).

## <a name="modal-dialog-boxes"></a>Modálních dialogových oken
 V rozšíření sady Visual Studio by měl vytváření modálních dialogových oken odvozením z <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName>, což vám umožňuje řídit jejich a zbývající části uživatelského rozhraní. Další informace najdete v tématu [vytvoření a správa modálních dialogových oken](../extensibility/creating-and-managing-modal-dialog-boxes.md).

## <a name="see-also"></a>Viz také:
- [Vytváření rozšíření pomocí panelu nástrojů](../extensibility/creating-an-extension-with-a-tool-window.md)