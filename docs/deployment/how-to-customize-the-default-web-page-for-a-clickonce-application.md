---
title: 'Postupy: Úprava výchozí webové stránky pro aplikaci ClickOnce | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Publish.htm Web page
- ClickOnce deployment default Web page
- deploying applications [ClickOnce], publishing
- publishing, ClickOnce
ms.assetid: 418de18c-bee9-4f24-9cd9-0252d175070d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4a4fc4d69e8bf0a3ef13a8a06e652c8be217a1c6
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60106324"
---
# <a name="how-to-customize-the-default-web-page-for-a-clickonce-application"></a>Postupy: Úprava výchozí webové stránky pro aplikaci ClickOnce
Při publikování aplikace ClickOnce k webu, je automaticky generována a spolu s aplikace publikována na webové stránce. Výchozí stránka obsahuje název aplikace a odkazy na instalaci aplikace, instalace požadovaných součástí nebo nápovědu na webu MSDN.

> [!NOTE]
>  Skutečné odkazy, které se zobrazí na stránce jsou závislé na počítači, kde je zobrazení stránky a co požadavky jsou včetně.

 Název výchozí webové stránky je *Publish.htm*; můžete změnit název v **Návrháře projektu**. Další informace najdete v tématu [jak: Určení stránky publikování pro aplikaci ClickOnce](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md).

 *Publish.htm* webová stránka je publikován pouze v případě, že byla zjištěna novější verze.

> [!NOTE]
>  Změny provedené na vaše **publikovat** nastavení nebude mít vliv *Publish.htm* stránky s jednou výjimkou: Pokud přidáte nebo odeberete požadavky po počátečním publikování, bude seznam požadovaných součástí nadále již nebudou přesné. Je potřeba upravit text pro požadovaný odkaz tak, aby odrážely změny.

### <a name="to-customize-the-publish-web-page"></a>Chcete-li přizpůsobit publikované webové stránky

1. Publikování aplikace ClickOnce k umístění webu. Další informace najdete v tématu [jak: Publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).

2. Na webovém serveru, otevřete *Publish.htm* souboru v Visual Web Designer nebo jiného editoru HTML.

3. Přizpůsobení stránky podle potřeby a uložte ho.

4. Volitelné. Chcete-li zabránit přepsání publikovat vlastní webovou stránku sady Visual Studio, zrušte zaškrtnutí políčka **automaticky generovat webovou stránku nasazení po každé publikovat** v **možnosti publikování** dialogové okno.

## <a name="see-also"></a>Viz také:
- [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)
- [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Postupy: Instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
- [Postupy: Určení stránky publikování pro aplikaci ClickOnce](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)