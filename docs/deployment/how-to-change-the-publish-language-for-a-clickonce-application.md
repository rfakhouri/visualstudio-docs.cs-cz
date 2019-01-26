---
title: 'Postupy: Změnit jazyka publikování pro aplikaci ClickOnce | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Publish language property
- ClickOnce deployment, changing publish language
- publishing, ClickOnce
ms.assetid: ef5024c4-cda1-4970-bc75-32a2a10c92c3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 67ac7693d4332c4dc5d6eae3fb89cf3e9a9c2384
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54953027"
---
# <a name="how-to-change-the-publish-language-for-a-clickonce-application"></a>Postupy: Změna jazyka publikování pro aplikaci ClickOnce

Při publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, uživatelské rozhraní zobrazí během instalace výchozí nastavení jazykové verze vývojového počítače. Pokud publikujete lokalizované aplikace, je potřeba zadat jazykovou verzi tak, aby odpovídaly lokalizovanou verzi. Toto je určeno `Publish language` vlastnost pro váš projekt.

`Publish language` Vlastnost lze nastavit **možnosti publikování** dialogové okno, přístupné **publikovat** stránku **Návrháře projektu**.

> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [Resetovat nastavení](../ide/environment-settings.md#reset-settings).

## <a name="to-change-the-publish-language"></a>Chcete-li změnit jazyk publikování

1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.

2.  Klikněte na tlačítko **publikovat** kartu.

3.  Klikněte na tlačítko **možnosti** tlačítko Otevřít **možnosti publikování** dialogové okno.

4.  Klikněte na tlačítko **popis**.

5.  V **možnosti publikování** dialogové okno pole, vyberte jazyk a jazykovou verzi z **jazyk publikování** rozevíracího seznamu a pak klikněte na tlačítko **OK**.

## <a name="see-also"></a>Viz také:

- [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Postupy: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)