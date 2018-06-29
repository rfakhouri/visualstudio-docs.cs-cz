---
title: Dialogové okno Upřesnit nastavení zabezpečení
ms.date: 06/27/2018
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
ms.openlocfilehash: 3910383733171775bd1f25e230cbb896648034bb
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089539"
---
# <a name="advanced-security-settings-dialog-box"></a>dialogové okno Upřesnit nastavení zabezpečení

Toto dialogové okno umožňuje zadat nastavení zabezpečení související s laděním v zóně.

![Dialogové okno Upřesnit nastavení zabezpečení v sadě Visual Studio](../media/advanced-security-settings.png)

Pro přístup k tohoto dialogového okna, vyberte uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **zabezpečení** kartě. Na **zabezpečení** vyberte **povolení nastavení zabezpečení ClickOnce**, klikněte na tlačítko **Toto je aplikace s částečnou důvěryhodností**a pak klikněte na tlačítko **Upřesnit**.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

**Udělit přístup k aplikaci do jeho lokality původu**

Pokud vyberete toto políčko, aplikaci přístup na webový server nebo sdílená složka serveru, na kterém je publikována. Ve výchozím nastavení je tato možnost vybrána.

**Ladění této aplikace, jako kdyby byly staženy z následující adresy URL**

Pokud budete muset povolit aplikaci pro přístup na webový server nebo sdílená složka serveru odpovídající **adresy URL instalace** jste zadali na **publikovat** stránky, zadejte tuto adresu URL. Tato možnost je dostupná jenom v případě **udělit přístup k aplikaci do jeho lokality původu** je vybrána.

## <a name="see-also"></a>Viz také:

- [Stránka Zabezpečení, Návrhář projektu](../../ide/reference/security-page-project-designer.md)