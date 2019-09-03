---
title: Publikovat do složky
ms.date: 04/02/2019
helpviewer_keywords:
- deployment, website
ms.assetid: e963fb4b-6d32-4d45-86bb-ef7e4d3028b0
author: sayedihashimi
ms.author: sayedha
manager: unniravindranathan
ms.prod: visual-studio-mac
ms.openlocfilehash: e22176d2188df92f0956f88c912d48cb9c954dd9
ms.sourcegitcommit: fe212f8960d7882a1b0fdae9e22f008996aacf3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222774"
---
# <a name="publish-a-web-app-to-a-folder-using-visual-studio-for-mac"></a>Publikování webové aplikace do složky pomocí Visual Studio pro Mac

K publikování aplikací ASP.NET Core do složky můžete použít nástroj pro publikování.

## <a name="prerequisites"></a>Požadavky

- Je nainstalována [aplikace Visual Studio 2019 pro systém Mac](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs4mac2019) s povoleným ASP.NET Core.
- ASP.NET Core projekt. Pokud projekt ještě nemáte, můžete [vytvořit nový](https://docs.microsoft.com/visualstudio/mac/create-new-projects?view=vsmac-2019).

## <a name="publish-to-folder"></a>Publikování do složky

Pomocí Visual Studio pro Mac můžete publikovat ASP.NET Core projekty do složky pomocí nástroje Publikovat. Po publikování do složky můžete přenést soubory na webový server, abyste je získali do jiného prostředí. Chcete-li publikovat do složky, postupujte podle těchto kroků.

 1. V Oblast řešení klikněte pravým tlačítkem myši na projekt a vyberte možnost **publikovat**.

    ![Místní nabídka publikovat](media/publish-context-menu.png)

 2. Pokud jste tento projekt publikovali už dřív, zobrazí se v nabídce profil publikování. Kliknutím na tento profil publikování spusťte proces publikování.

 3. Chcete-li tento projekt publikovat do složky poprvé, vyberte možnost **publikovat do složky** .

    ![Místní nabídka publikovat do složky](media/publish-to-folder-context-menu.png)

 4. Zobrazí se dialogové okno **publikovat do složky** . V tomto dialogovém okně můžete přizpůsobit složku, do které bude projekt publikován. K provedení tohoto postupu nebo vložení do cesty můžete použít tlačítko **Procházet** .

 5. Po kliknutí na **publikovat** se stane několik věcí. Nejprve je vytvořen profil publikování. Profil publikování je soubor MSBuild, který se importuje do projektu během procesu publikování. Obsahuje vlastnosti, které se používají během procesu publikování. Tyto soubory jsou uloženy v `Properties/PublishProfiles` nástroji a mají příponu. `.pubxml` V dalším kroku se spustí proces publikování. Průběh můžete sledovat sledováním stavového řádku v Visual Studio pro Mac.

    ![Stavový řádek IDE se stavem publikování](media/publish-to-folder-status-bar.png)

 6. Po úspěšném dokončení publikování se otevře okno hledání ve složce pro publikování. Teď, když je profil publikování vytvořený, se zobrazí v místní nabídce publikovat.

    ![Místní nabídka publikovat s profilem složky](media/publish-context-menu-with-folder-profile.png)

 7. Pokud chcete projekt publikovat znovu se stejnými nastaveními, můžete kliknout na profil v místní nabídce publikovat.

## <a name="customize-publish-options"></a>Přizpůsobení možností publikování

Chcete-li změnit název profilu publikování (který se zobrazí v místní nabídce publikovat), přejmenujte soubor profilu publikování. Ujistěte se, že neměníte příponu souboru (`.puxbml`).

Chcete-li změnit cestu ke složce pro publikování, otevřete profil publikování a `publishUrl` upravte hodnotu.

Chcete-li změnit použitou konfiguraci sestavení, změňte `LastUsedBuildConfiguration` vlastnost v profilu publikování.
