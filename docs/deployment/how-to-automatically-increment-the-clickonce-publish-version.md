---
title: 'Postupy: Automaticky ClickOnce Inkrementace verze publikování | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], incrementing publish version automatically
- Publish Version property, incrementing
- ClickOnce deployment, incrementing publish version automatically
- publishing, ClickOnce
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b17a0c54ba0efa7a6eb732de45fa7d1644577041
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53861387"
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>Postupy: Automaticky ClickOnce Inkrementace verze publikování

Při publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, změna `Publish Version` vlastnosti způsobí, že aplikace má být publikován jako aktualizace. Ve výchozím nastavení, Visual Studio automaticky zvýší `Revision` počet `Publish Version` pokaždé, když publikujete aplikaci.

Toto chování lze zakázat na **publikovat** stránku **Návrháře projektu**.

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [Resetovat nastavení](../ide/environment-settings.md#reset-settings).

## <a name="to-disable-automatically-incrementing-the-publish-version"></a>Chcete-li zakázat automatické zvyšování verzi publikování

1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.

2.  Klikněte na tlačítko **publikovat** kartu.

3.  V **publikovat verzi** části, zrušte **automaticky zvyšovat číslo každé vydané verze** zaškrtávací políčko.

## <a name="see-also"></a>Viz také:

- [Postupy: Nastavení publikování ClickOnce verze](../deployment/how-to-set-the-clickonce-publish-version.md)
- [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Postupy: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)