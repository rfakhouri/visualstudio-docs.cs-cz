---
title: Správa verzí TF
description: Připojení k serveru Team Foundation Server nebo Visual Studio Team Services s verzí Team Foundation.
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: f892209faeb06ca703d28016457e9ba4ab86ccda
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/08/2018
---
# <a name="connecting-to-team-foundation-version-control"></a>Připojení do správy verzí Team Foundation 

Visual Studio Team Services (služby VSTS) a Team Foundation Server (TFS), zadejte dva modely verzí: Git, který je distribuován verzí a Team Foundation verze ovládacího prvku (TFVC), což je centralizované správy verzí. Tento článek obsahuje přehled a výchozí bod pro používání správy verzí Team Foundation pomocí sady Visual Studio for Mac.

> [!NOTE]
> **Poznámka:**: podpora správy verzí Team Foundation je aktuálně ve verzi preview a některé funkce není ještě plně funkční. Další změny, je stále pocházet!

## <a name="requirements"></a>Požadavky

* Visual Studio pro Mac verze 7.5 nebo novější.
* Visual Studio Team servery nebo Team Foundation Server 2013 a novější
* Projekt sady Visual Studio Team Services nebo Team Foundation Server nakonfigurovaný na použití správy verzí Team Foundation.

## <a name="installation"></a>Instalace

Z v sadě Visual Studio pro Mac, vyberte **Visual Studio > rozšíření...**  nabídky. Vyhledejte "TF verzí" a nainstalovat **správy verzí Team Foundation** rozšíření. Restartujte IDE po zobrazení výzvy.

## <a name="using-the-add-in"></a>Pomocí doplňku

Po instalaci rozšíření, vyberte **verzí > sady TFS nebo služby VSTS > připojte se k správě verzí Team Foundation...**  nabídky. 

![Přidání serveru TFVC](media/tfvc-add-remove-server.png)


Vyberte buď Visual Studio Team Services nebo Team Foundation Server, abyste mohli začít:

![Připojení se serverem TFVC](media/tfvc-choose-server-type.png)

Zadejte přihlašovací údaje: 

![Přihlaste se k serveru TFVC](media/tfvc-login.png)

Zvolte projektů, které chcete získat přístup: 

![Zvolte projekty](media/tfvc-choose-projects.png)

Chcete pokračovat, zavřete dialogová okna a potom pomocí **verzí > sady TFS nebo služby VSTS > Průzkumník správy zdrojového kódu** nabídku k nalezení zdroje.

> [!WARNING]
> **Známý problém**: V této verzi preview poprvé otevřete Průzkumník správy zdrojového kódu, budete muset vytvořit nový pracovní prostor.

![Průzkumník správy zdrojového](media/tfvc-source-explorer.png)

Z Průzkumník správy zdrojového kódu můžete procházet vašeho zdrojového kódu na serveru a proveďte následující akce:

- Správa pracovních prostorů (vytvořit, upravit nebo odstranit).
- Přechod mezi strukturu projektu.
- Mapovat projekty.
- Získáte projekty.
- Zamknout & odemknutí soubory.
- Přejmenování souborů.
- Odstraňte soubory.
- Přidáte nový soubor.
- Mrkni se.
- Přihlásit se.
- Zobrazení historie změn.
- Porovnejte změny.

## <a name="creating-a-new-workspace"></a>Vytváření nového pracovního prostoru

V Průzkumník správy zdrojového kódu, klikněte na **spravovat pracovní prostory** tlačítko. 

![Správa pracovních prostorů](media/tfvc-manage-workspaces.png)

Klikněte na **přidat** vytvořit nový pracovní prostor.

![Vytvořit pracovní prostor](media/tfvc-create-workspace.png)

Zadejte název pro pracovní prostor a pak klikněte na tlačítko **přidat pracovní složku** k mapování projektu do místní složky v počítači.

Až budete hotoví, klikněte na tlačítko **OK**, pak zavřete dialogové okno Spravovat pracovní prostory. Nyní jste připravení získání souborů, když Průzkumník správy zdrojového kódu a začít.