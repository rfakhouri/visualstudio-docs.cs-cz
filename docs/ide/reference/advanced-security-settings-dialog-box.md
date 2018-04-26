---
title: Dialogové okno Upřesnit nastavení zabezpečení
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.err.debug_in_zone_no_hostproc
helpviewer_keywords:
- Advanced Security Settings dialog box
ms.assetid: 2e7aefe9-6d20-4f3e-b257-aee1ebcc6f5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6fec353f6ede2a9d2f99a8dfc19611577bbc6160
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="advanced-security-settings-dialog-box"></a>Dialogové okno Upřesnit nastavení zabezpečení
Toto dialogové okno umožňuje zadat nastavení zabezpečení související s laděním v zóně.

 Pro přístup k tohoto dialogového okna, vyberte uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **zabezpečení** kartě. Na **zabezpečení** vyberte **povolení nastavení zabezpečení ClickOnce**, klikněte na tlačítko **Toto je aplikace s částečnou důvěryhodností**a pak klikněte na tlačítko **Upřesnit**.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Ladění tuto aplikaci s vybraným nastavením oprávnění** Pokud vyberete toto políčko, na vybrané sadě oprávnění **zabezpečení** stránky se používá během ladění. Ve výchozím nastavení je tato možnost vybrána.

 Pro ladění v zóně zabezpečení fungovat, musí být tato možnost povolená; Navíc **povolit sady Visual Studio proces hostování** možnost (k dispozici na **ladění** stránky **Návrhář projektu**) musí být povolena.

 Pro aplikace WPF webového prohlížeče projekty **ladění tuto aplikaci s vybraným nastavením oprávnění** je zaškrtnuta možnost a zakázaná možnost.

 **Udělit přístup k aplikaci do jeho lokality původu** Pokud vyberete toto políčko, aplikaci přístup na webový server nebo sdílená složka serveru, na kterém je publikována. Ve výchozím nastavení je tato možnost vybrána.

 **Ladění této aplikace, jako kdyby byly staženy z následující adresy URL** Pokud budete muset povolit aplikaci pro přístup na webový server nebo sdílená složka serveru odpovídající **adresy URL instalace** jste určili na **Publikovat** stránky, zadejte tuto adresu URL. Tato možnost je dostupná jenom v případě **udělit přístup k aplikaci do jeho lokality původu** je vybrána.

## <a name="see-also"></a>Viz také

- [Stránka Zabezpečení, Návrhář projektu](../../ide/reference/security-page-project-designer.md)