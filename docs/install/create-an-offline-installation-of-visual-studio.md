---
title: "Vytvoření Offline instalace sady Visual Studio | Microsoft Docs"
description: "Zjistěte, jak k instalaci sady Visual Studio v režimu offline."
ms.custom: 
ms.date: 08/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 8b0902c7e2d3c2b51ecd915647a3e8a03e49c641
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="create-an-offline-installation-of-visual-studio-2017"></a>Vytvoření offline instalace Visual Studio 2017

Jsme chtěli instalační program Visual Studio 2017 fungovat i v celé řadě podmínek, sítě a počítače.

- Nový model založené na pracovním vytížení znamená, že budete muset stáhnout úplně menší než u starších verzí sady Visual Studio: malé jako 300 MB nejmenší instalace;
- Ve srovnání s obecný "ISO" nebo soubor zip, jsme stáhnout pouze balíčky, které potřebujete pro váš počítač. Například jsme nestahovat 64-bit soubory nepotřebujete je;
- Během procesu instalace pokusíme tři různé stažení technologie (WebClient, BITS a WinInet) Chcete-li minimalizovat narušení s antivirový a proxy softwaru;
- Soubory, budete muset nainstalovat Visual Studio se distribuují v síti globální doručování, takže jsme můžete získat pro vás z místního serveru.

Doporučujeme vám, že zkusíte [instalačního programu sady Visual Studio webové](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)&mdash;myslíme si, naleznete je dobré prostředí.

 > [!div class="button"]
 > [Stáhněte si Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)
<br/>

Pokud chcete nainstalovat do offline režimu, protože připojení k Internetu je k dispozici nebo nespolehlivé, viz [nainstalovat Visual Studio 2017 na malou šířkou pásma nebo nespolehlivé mezi sítě v prostředích](../install/install-vs-inconsistent-quality-network.md). Příkazového řádku můžete použít k vytvoření místní mezipaměti souborů, které potřebujete k dokončení instalace v režimu offline. Tento proces nahradí soubory ISO k dispozici pro předchozí verze.

> [!NOTE]
> Pokud jste správce organizace, který chce provést nasazení sady Visual Studio 2017 k síti klientské pracovní stanice, které jsou bránou firewall z Internetu, najdete v našich [vytvořit sítě instalaci sady Visual Studio 2017](../install/create-a-network-installation-of-visual-studio.md) a [Zvláštní požadavky pro instalaci sady Visual Studio v režimu offline](../install/install-visual-studio-in-offline-environment.md) stránky.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku Tipy pro odstraňování potíží. Taky můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj v prostředí Visual Studio IDE nebo ke sdílení návrh s nám na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi. Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio) (vyžaduje [Githubu](https://github.com/) účtu).
