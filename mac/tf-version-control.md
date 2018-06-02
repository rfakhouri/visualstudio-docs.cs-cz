---
title: Správa verzí TF
description: Připojení k serveru Team Foundation Server nebo Visual Studio Team Services s verzí Team Foundation.
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 58d0fc5c31b02574661f8b86a4ae8bcaf393be3a
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34693770"
---
# <a name="connecting-to-team-foundation-version-control"></a>Připojení do správy verzí Team Foundation 

> [!NOTE]
> **Poznámka:**: podpora správy verzí Team Foundation je aktuálně ve verzi preview a některé funkce není ještě plně funkční. Rádi zpětnou vazbu od vás na všechny problémy v [komunity vývojářů](https://developercommunity.visualstudio.com/spaces/41/index.html). Další změny jsou stále pocházet!

Visual Studio Team Services (služby VSTS) a Team Foundation Server (TFS), zadejte dva modely verzí: Git, který je distribuován verzí a Team Foundation verze ovládacího prvku (TFVC), což je centralizované správy verzí. Tento článek obsahuje přehled a výchozí bod pro používání správy verzí Team Foundation pomocí sady Visual Studio for Mac.

## <a name="requirements"></a>Požadavky

* Visual Studio pro Mac verze 7.5 nebo novější.
* Visual Studio Team Services a serveru Team Foundation Server 2013 a novější
* Projekt sady Visual Studio Team Services nebo Team Foundation Server nakonfigurovaný na použití správy verzí Team Foundation.

## <a name="installation"></a>Instalace

V sadě Visual Studio pro Mac, zvolte **Visual Studio > rozšíření...**  z nabídky. V **Galerie** vyberte **verzí > správy verzí Team Foundation pro TFS a služby VSTS** a klikněte na tlačítko **instalaci...** :

  ![Správce rozšíření](media/tfvc-install.png) 

Postupujte podle pokynů k instalaci rozšíření. Po instalaci, restartujte rozhraní IDE.

## <a name="using-the-add-in"></a>Pomocí doplňku

Po instalaci rozšíření, vyberte **verzí > sady TFS nebo služby VSTS > připojte se k správě verzí Team Foundation...**  položku nabídky. Klikněte na tlačítko **přidat** přidat nový účet: 

![Přidání serveru TFVC](media/tfvc-add-remove-server.png)

Vyberte buď Visual Studio Team Services nebo Team Foundation Server, abyste mohli začít:

![Připojení se serverem TFVC](media/tfvc-choose-server-type.png)

Zadejte své přihlašovací údaje a klikněte na tlačítko **přihlášení**: 

![Přihlaste se k serveru TFVC](media/tfvc-login.png)

Jakmile úspěšně jste přihlášení, vyberte projekty, které chcete pro přístup k a stiskněte klávesu **OK**: 

![Zvolte projekty](media/tfvc-choose-projects.png)

Vyberte **verzí > sady TFS nebo služby VSTS > Průzkumník správy zdrojového kódu** položku otevřete Průzkumníka správy zdrojového kódu umožňuje procházet zdroji.

> [!IMPORTANT]
> **Známý problém**: V této verzi preview poprvé otevřete Průzkumník správy zdrojového kódu, budete muset [vytvořit nový pracovní prostor](#creating-a-new-workspace).

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

Klikněte **přidat** tlačítko Vytvořit nový pracovní prostor.

![Vytvořit pracovní prostor](media/tfvc-create-workspace.png)

Zadejte název pro pracovní prostor a pak klikněte na tlačítko **přidat pracovní složku** k mapování projektu do místní složky v počítači.

Až budete hotoví, klikněte na tlačítko **OK**, pak zavřete dialogové okno Spravovat pracovní prostory. Nyní jste připravení získání souborů, když Průzkumník správy zdrojového kódu a začít.

## <a name="troubleshooting"></a>Poradce při potížích

### <a name="problems-using-basic-authentication"></a>Problémy při použití základního ověřování

Existuje několik různých možností k provedení ověřování pomocí serveru:

- OAuth
- Základní
- NTLM

Abyste mohli používat základní ověřování je potřeba povolit **alternativní ověřovací pověření** v služby VSTS podle následujících kroků:

1. Přihlaste se jako vlastníka účtu ke svému účtu služby VSTS (https://{youraccount}.visualstudio.com).
2. Na váš účet nástrojů, vyberte na zařízení ikonu a vyberte **zásad**: ![vybraná možnost nastavení zásad](media/tfvc-auth2.png) 
3. Zkontrolujte nastavení připojení k aplikaci. Změna těchto nastavení v závislosti na vaše zásady zabezpečení: ![vybraná možnost nastavení zásad](media/tfvc-auth.png)  

### <a name="i-do-not-see-anything-in-tfvc"></a>Nejsou vidět v TFVC nic

Nastavit až Team Foundation verze ovládacího prvku (TFVC) na vývojářském počítači, můžete **musí** vytvořit pracovní prostor, jak je popsáno v [vytváření nový pracovní prostor](#creating-a-new-workspace) části.

V Průzkumník správy zdrojového kódu, stiskněte **spravovat pracovní prostory** tlačítko. Postupujte podle kroků pro mapování týmový projekt do složky na vývojářském počítači.

### <a name="i-do-not-see-any--all-of-my-projects"></a>Nevidím žádné nebo všechny mých projektů

Po ověření měli byste vidět seznam projektů. Ve výchozím nastavení se zobrazí pouze projektů sady TFS pro. Pokud chcete zobrazit jiné typy projektů, zaškrtněte políčko "Viz všechny projekty".

Mějte na paměti, že projekty, které jsou na serveru se nezobrazí, pokud nemáte dostatečná oprávnění.

#### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>Zobrazuje chyba "nelze vytvořit pracovní prostor. Zkuste to prosím znovu"

Při pokusu o [vytvořit nový pracovní prostor](#creating-a-new-workspace), měli byste zajistit splnění následujících podmínek:

- Použití žádné neplatné znaky v názvu pracovního prostoru.
- Název musí být kratší než 64 znaků.
- Místní cesta nemůže být použit jiných pracovních prostorech.