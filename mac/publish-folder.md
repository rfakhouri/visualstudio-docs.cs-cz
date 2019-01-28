---
title: Publikovat do složky – Visual Studio pro Mac
ms.date: 01/22/2019
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: e963fb4b-6d32-4d45-86bb-ef7e4d3028b0
author: sayedihashimi
ms.author: sayedha
manager: unniravindranathan
ms.prod: visual-studio-mac-dev15
ms.openlocfilehash: a71b873a2c853d5b90aea2853d73eb1fe8f6abb6
ms.sourcegitcommit: 447f2174bdecdd471d8a8e11c19554977db620a0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/28/2019
ms.locfileid: "55090165"
---
# <a name="publish-a-web-app-to-a-folder-using-visual-studio-for-mac"></a>Publikování webové aplikace do složky pomocí sady Visual Studio pro Mac

Nástroj publikování můžete použít k publikování aplikace ASP.NET Core do složky.

## <a name="prerequisites"></a>Požadavky

 - [Visual Studio 2017 for Mac](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs4mac2017) nainstalované s ASP.NET Core povolena.
 - Projekt ASP.NET Core. Pokud projekt ještě nemáte, můžete si [vytvořte novou](https://docs.microsoft.com/visualstudio/mac/create-new-projects?view=vsmac-2017).

## <a name="publish-to-folder"></a>Publikovat do složky

Pomocí sady Visual Studio for Mac můžete publikovat projekty ASP.NET Core do složky pomocí nástroje Publish. Po publikování do složky můžete převést soubory na webový server se dá stáhnout do jiného prostředí. Chcete-li publikovat do složky postupujte podle těchto kroků.

 1. V oblasti řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**.

    ![Místní nabídka publikovat](media/publish-context-menu.png)

 2. Pokud jste dříve publikovali tento projekt, zobrazí se vám v nabídce profilu publikování. Vyberte tento profil publikování, chcete-li zahájit proces publikování.

 3. První přihlášení publikujte tento projekt do složky, vyberte **publikovat do složky**

    ![Publikovat do složky místní nabídky](media/publish-to-folder-context-menu.png)

 4. **Publikovat do složky** se zobrazí dialogové okno. V tomto dialogovém okně můžete upravit složku, kde bude projekt publikován. Můžete použít **Procházet** tlačítko k tomu, nebo zkopírujte cestu.

 5. Po kliknutí na tlačítko **publikovat** stane pár věcí. Nejprve se vytvoří profil publikování. Profil publikování se soubor MSBuild, který je do projektu importován během procesu publikování. Obsahuje vlastnosti, které se používají během procesu publikování. Tyto soubory se ukládají v `Properties/PublishProfiles` a mají příponu `.pubxml`. V dalším kroku se spustí proces publikování. Průběh můžete monitorovat ve stavovém řádku v sadě Visual Studio pro Mac.

    ![Stavový řádek IDE se stav publikování](media/publish-to-folder-status-bar.png)

 6. Po úspěšném dokončení publikování otevře se okno hledání do složky publikovat. Teď, když byl vytvořen profil publikování, zobrazí se v místní nabídce publikovat.

    ![Místní nabídka s složku profilu publikování](media/publish-context-menu-with-folder-profile.png)

 7. Chcete-li publikovat projekt znovu se stejným nastavením, které můžete kliknout na profil v místní nabídce publikovat.

## <a name="customize-publish-options"></a>Upravit možnosti publikování

Chcete-li změnit název profilu publikování (který se zobrazí v místní nabídce publikování), přejmenujte soubor profilu publikování. Ujistěte se, že není změňte příponu souboru (`.puxbml`).

Chcete-li změnit cesty ke složce publikovat, profil publikování otevřít a upravit `publishUrl` hodnotu.

Chcete-li změnit konfiguraci sestavení, který se používá, změňte `LastUsedBuildConfiguration` vlastnost v profilu publikování.